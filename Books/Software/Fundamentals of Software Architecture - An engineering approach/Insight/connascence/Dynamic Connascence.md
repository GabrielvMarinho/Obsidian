runtime level coupling

## Types

1. Connascence of execution -> the order of execution is important, like a setSubject() before send()
2. Connascence of timing -> the timing of the execution of multiple components is important, like race condition
3. Connascence of value -> when values related to each other and must change together, like separate databases, more related to shared values
4. Connascence of identity -> occurs when several values related on one another and must change together, two modules sharing a queue, more related to shared objects


[[Connascence]]