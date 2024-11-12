It's a Branch. A copy of the code where the dev can work separately.

to create a branch:
```
git branch name_of_the_branch
```

change to differente branch:
```
git checkout name_of_the_branch
```

visualize branches:
```
git branch

//to visualize remote branches
git branch -a
```

to delete branches:
```
git branch -d nomeDoBranchLocal

//to delete remote branches
git push origin --delete nomeDoBranchRemoto
```

to "push" a branch:
```
git push --set-upstream origin nomeDoBranch
```

clone branch remota:
```
git checkout -b "nome-da-branch-local" origin/"nome-da-branch-remota"
```