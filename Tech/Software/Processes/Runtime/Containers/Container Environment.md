Container runtimes run applications in isolated environments called containers, but unlike virtual machines, containers share the host’s kernel.  

When you use a minimal base image (like a lightweight Linux filesystem), it provides all necessary user-space files, similar to an OS but **without including the kernel**.  

This makes containers faster and smaller than virtual machines because they don’t virtualize hardware or boot full operating systems.

However, if the host operating system’s kernel is different from what the container expects (for example, running a Linux container on a Windows host), the container runtime may launch a lightweight virtual machine to provide the needed kernel.  

So, while containers are not virtual machines by design, kernel mismatches can cause the runtime to rely on a VM behind the scenes.



## Networking

- When a container starts, the container runtime (like Docker or Kubernetes) typically creates a virtual network interface for the container.
    
- This interface gets an **IP address** from the virtual network (for example, from a Docker bridge network or a Kubernetes CNI network).