

Docker is not that easy.  
  
Ever heard about how "A docker container runs you software in an isolated environment, but don't confuse it with a virtual machine!", what does that even mean?  
  
When you build a docker image you have to explicitly tell how the software will be run, you would write something like "FROM alpine" to indicate that your image need to run in an alpine like env, this will pull a BASE IMAGE from docker hub, with everything set for you to use.  
  
This base image consists of a lot of Operating System features, like a file or port system, what It will never have though, is the kernel, that's the main reason why Its "lighter than a virtual machine", when you start the container, the host machine's kernel split Its capacity to attend both processes, your main OS process and the docker container itself running.  
  
Going deeper into It, you would see that an alpine env would never be able to use your Windows kernel (if you have Windows), because It's expecting Linux, what is done then? Well, a virtual machine is run, the process will only share kernel resources if both parts demand from the same kernel.  
  
So in the end, It just came back to being a VM.