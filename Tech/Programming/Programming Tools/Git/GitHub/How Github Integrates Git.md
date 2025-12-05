When you reset to a certain commit, git status wil point something has changed, this is ok and straight forward.

When you reset to a commit, git still stores the changes and wait for the default time of weeks for the garbage collector to delete it.

When you clean the not used objects with the garbage collector, github doesnt notice the difference.

When you clone a repository that had dangling commits, you dont have those dangling objects, its like gitlab (at least gitlab) runs a gc command to clean all objects every time you commit to  it

# GitLab doesn't preserve dangling objects for 90 days as it should (vanila git does)
