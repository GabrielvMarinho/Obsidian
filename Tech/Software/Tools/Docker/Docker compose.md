A [[Docker]] tool used to run and manage multiple **[[Docker Container|Docker containers]]** simultaneously, as well as to automatically configure network bridges and shared resources between them.


## **Volumes** 

Is a feature of docker compose to share file/directories to multiple containers

### **Bind mounts**

Mounts a specific folder or file from the host’s filesystem directly into one or more containers (docker compose).

this works by giving access to the containers for the exact path of the directory (awesome for [[Embedded Database|Embedded Databases]] like [[SQLite]])

### **Docker Volumes**

Docker-managed storage on the host that can be shared and persisted independently of containers.