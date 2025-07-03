resets every change from on a specific point

`git reset` lets you move your branch back in time — the commits are removed from history, but their changes can be kept in your working directory, ready to edit, recommit, or discard (depends on which type of reset).

changes the branch pointer and the head to the specific commits and keeps changes staged (loses commits order, just keeps the content)
```bash
git reset <commit-hash>
# now to save the changes
git push origin <branch-name> --force
```


changes the branch pointer and the head to the specific commits and delete changes
```bash
git reset --hard <commit-hash>
# now to save the changes
git push origin <branch-name> --force
```
