The ingress is a [[Kubernetes]] resource used to set the rules on how requests should be handled in the application, you can expose it via [[Service]]s (however, those lack important functionalities like url routing).

you can set for /api to go to a service or /frontend to go to a service
[[Ingress Controller]] will the resource that will actually apply those rules, based on the ingress

check [[Consistent Service Ip Assigning]]

