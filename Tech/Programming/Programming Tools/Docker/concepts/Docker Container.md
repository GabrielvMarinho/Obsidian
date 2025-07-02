
An isolated [[Process]] to run instance of a single [[Docker Image]]




## Internal Networking

A **Docker image**, when run as a container, operates in its own [[Docker Virtual Networking Environment]]. Each container receives a **virtual IP address**, this IP can only be accessed within Docker’s virtual network, not directly from the host machine or the internet.

To allow external access (e.g., from your browser), you must **map a port on your host machine** to a port exposed by the container. For example, to access a container's port `8080`, you might run:

`docker run -p 8080:8080 my-image`

When working with **multiple containers** (like a frontend and backend), they must be connected to the **same Docker network** to communicate (by default they communicate to the default bridge). This is commonly handled using [[Docker compose]], which creates an isolated network where containers can reference each other by name.