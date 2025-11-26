a process to turn a [[Virtual memory]] address to a [[Physical memory]] address

a process might start at 0 for who is looking it from the inside, but when starting, the [[Operating System]] sets the base, that number could be 64kb for example (it means the process's internal 0 is actually 64kb for the whole memory)

so the [[CPU]] translates the physical address as equals to = virtual address + base

### the bounds

its basically a number that sets the bounds of a process, that could be 16kb for example, anything not inside that would trigger an exception and likely kill the process