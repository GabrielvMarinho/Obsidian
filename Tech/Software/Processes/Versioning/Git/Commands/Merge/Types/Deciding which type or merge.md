The two most common forms ar the normal merge and the fast forward merge, to programatically decide which you will be done, first git finds the merge-base point.

to find the merge-base, git uses an algorithm to find the latest common commit, in this case below, the program will go through the parents of commit feature until it it finds that its correlated to the commit C, C would be set as the merge-base, since the common point is the latest commit of main, this is a fastforward commit.

A---B---C (HEAD -> main)
         \
          D---E (feature)


In the next example we have the common ancestor or the merge-base as being B, so the ancestor is not the latest commit of main, meaning this a normal merge that will generate another commit.

A---B---C (HEAD -> main)
      \
       D---E (feature)


## The algorithm

1. **Get the current commit hash** – this is where your current branch (e.g., `main`) is pointing.
    
2. **Get the commit hash of the branch you want to merge** (e.g., `feature`). This is the starting point for your search.
    
3. **Initialize an array** (called `ancestors`) with that starting commit hash (`branchToMerge`). This array will store all the commits you’ll examine.
    
4. Then, **enter a loop** where you:
    
    - Take the current hash from the array (by position).
        
    - If this hash equals your current commit hash, you’ve found it — a **fast-forward merge is possible**.
        
    - If not, look at the parents of this commit in the graph and **add each parent to the array**.
        
5. **Repeat this process**, moving through the array, adding parents as you go, until either:
    
    - You find the current commit hash (✅ fast-forward possible), or
        
    - You finish traversing the array without finding it (❌ fast-forward not possible).