When you reset to a certain commit, git status wil point something has changed, this is ok and straight forward.

When you reset to a commit, git still stores the changes and wait for the default time of weeks for the garbage collector to delete it.

Those objects dont represent any difference for github meaning if you trigger the garbage collector to delete those objects or keep it, github wouldnt notice the difference and Its not something you could commit.

The same way, if you clone a github repository, the objects dir would be empty.

How does git keep up with whats happening if the /objects dir is empty? or how does github store objects?