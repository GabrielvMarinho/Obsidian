An **Ingress** is a Kubernetes resource that routes external HTTP(S) traffic to [[Service|Services]] inside the cluster based on rules like path (`/`, `/api`) or host (`my-endpoint.com`).

I can point `my-endpoint.com/` to my application, but access the API directly through `my-endpoint.com/api`, and control it so that users cannot access that endpoint.

Its like there is two [[LoadBalancer]] but in one single configuration

It will always point to services -> if none is created, will check for [[ClusterIP]] ( the default )

check [[Consistent Service Ip Assigning]]
