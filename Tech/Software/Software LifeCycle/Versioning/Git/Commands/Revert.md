

`git revert` keeps your branch history intact by creating new commits that undo the changes of earlier ones — the original commits stay in the history, but their effects are reversed.
### Example usage:

```bash
git revert <commit-hash>
git push origin <branch-name>
```

- This adds a new commit on top of your branch that reverses the effects of `<commit-hash>`.
    
- No need to force push because history isn’t rewritten.```
