[[Git]] only store deltas of commits, not all the content itself.


useful article: [[Git Short Storage]].


### Short term

In the short term, git represents those objects loosely in the /objects dir, for long term effectiveness, those commits dont stay loose, they are rather stored in pack formats in the /objects/pack dir.

Which is basically the same way it was structured loosely, but in a more compressed way.
