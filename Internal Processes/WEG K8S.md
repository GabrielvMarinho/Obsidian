Steps to upload something to weg k8s system

1. create a component (api for example)
2. create a namespace for the project
3. attribuir o componente ao namespace
4. go to the component repositories and cnfigure the variables to use it
5. push something to maste for deploy
6. the result will be in either k8s.weg.net or k8s-qas.weg.net

## Ingress

for creating an ingress to configure both the dns and http requests routing there is a model in eaportal:
```yml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: minhaaplicacao-ingress
  namespace: prd-meu-namespace
  annotations:
    virtual-server.f5.com/ip: "controller-default"
    name: minhaaplicacao-ingress
    virtual-server.f5.com/clientssl: '[{ "bigIpProfile": "/Common/WILDCARD.WEG.NET"}]'
    ingress.kubernetes.io/ssl-redirect: "true"
    ingress.kubernetes.io/allow-http: "false"
spec:
  ingressClassName: f5
  rules:
    - host: minhaaplicacao.weg.net
      http:
        paths:
          - backend:
              service:
                name: minhaaplicacao-frontend-service
                port:
                  number: 80
            path: /
            pathType: Prefix
    - host: minhaaplicacao.weg.net
      http:
        paths:
          - backend:
              service:
                name: minhaaplicacao-backend-service
                port:
                  number: 3000
            path: /api
            pathType: Prefix
    - host: outro-dns-da-minhaaplicacao.weg.net
      http:
        paths:
          - backend:
              service:
                name: minhaaplicacao-outro-service
                port:
                  number: 3000
            path: /
            pathType: Prefix
```

this line:
```
    virtual-server.f5.com/ip: "controller-default"
```
is the ingress controller and is an annotation to set the ip of the app


to apply this you would need to create a repository and add this as a cicd file:
```yml
image: registry.weg.net/kubectl:envsubst  
  
stages:  
  - deploy  
  
deploy:QA:  
environment: qa  
stage: deploy  
tags:  
   - docker  
variables:  
   NAMESPACE: [namespace qa]  
   URL: [DNS QA]  
rules:   
   - if: '$CI_COMMIT_BRANCH == "master" || $CI_COMMIT_TAG != null || $CI_PIPELINE_SOURCE == "web"'  
     when: on_success  
   - if: '$CI_COMMIT_BRANCH != "master" && $CI_PIPELINE_SOURCE == "push"'  
     when: manual  
  
script:  
- mkdir -p /root/.docker  
- echo $DOCKER_AUTH_CONFIG > /root/.docker/config.json  
- envsubst  < ingress.yaml > ingress-var.yaml  
- cat ingress-var.yaml  
- kubectl --kubeconfig=$k8s_dev_op apply -f ingress-var.yaml --namespace $NAMESPACE  
  
deploy:PRD:  
environment: prd  
stage: deploy  
tags:  
   - docker  
variables:  
   NAMESPACE: [namespace prd]  
   URL: [DNS PRD]  
rules:   
   - if: '$CI_COMMIT_TAG != null'  
     when: manual  
script:  
- mkdir -p /root/.docker  
- echo $DOCKER_AUTH_CONFIG > /root/.docker/config.json  
- envsubst  < ingress.yaml > ingress-var.yaml  
- cat ingress-var.yaml  
- kubectl --kubeconfig=$k8s_prd_op apply -f ingress-var.yaml --namespace $NAMESPACE
```