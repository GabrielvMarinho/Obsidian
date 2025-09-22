Type of [[Service]] that exposes the application (cluster of [[Pods]]) on a port on each [[Tech/Software/Tools/Kubernetes/Node|Node]] IP 

if you have 3 nodes, you would be able to access from 3 different ips:
```
http://192.168.1.10:31000
http://192.168.1.11:31000
http://192.168.1.12:31000
```

accessible: externally through NodeIP:NodePort

