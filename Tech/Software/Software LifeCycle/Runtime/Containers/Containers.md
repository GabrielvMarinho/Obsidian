A container is a packaged and isolated [[Runtime]] environment that includes everything needed for an application to run

## Internal Networking

An image, when run as a container, operates in its own [[Virtual Network]]. Each container receives a **virtual IP address**, this IP can only be accessed within the virtual network, not directly from the host machine or the internet.

To allow external access (e.g., from your browser), you must **map a port on your host machine** to a port exposed by the container. For example, to access a container's port `8080`, you might run:

`docker run -p 8080:8080 my-image` (in case you are using docker)

When working with **multiple containers** (like a frontend and backend), they must be connected to the **same network** to communicate (by default they communicate to the default bridge). This is commonly handled using [[Declarative Multi-Container Application Orchestration]], 