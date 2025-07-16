You can and should have consistent IP Assigning for your service, so the dns can point to the same place if the cluster is killed and deployed back

## Example With Ingress

Create an Ingress resource with routing rules, and point your DNS to that IP to handle traffic to your app.
```yaml
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
      targetPort: 8080```

now both the api and frontend would be accessed through the same ip or dns

Notice something similar of a static IP could be done without the ingress