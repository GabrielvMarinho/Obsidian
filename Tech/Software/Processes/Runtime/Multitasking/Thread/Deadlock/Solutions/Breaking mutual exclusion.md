Could be done by:
1. Using resources that allow simultaneous use, like AtomicInteger in Java
2. increasing the number of resources so its greater or equal to the number of threads
3. checking that all your resources are free before seizing any