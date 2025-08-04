git garbage collector

```
git gc
```
clean all the loose objects and compress them in the .pack file.


delete all dangling commits
```
git reflog expire --expire-unreachable=now --all

git gc --prune=now
```