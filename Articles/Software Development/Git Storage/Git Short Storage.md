How does Git store the history of a repository?  
  
When it comes to history handling, everything is an object. There are 3 types:  
  
BLOB: An object representing the content of a file.  
  
TREE: An object representing a list of BLOBs, linking each BLOB with a file name (and some more metadata of each file). A TREE can also reference another TREE (a subdir basically).  
  
COMMIT: An object pointing to a TREE and holding more important info, like the committer.  
  
Each of these in Git receives a SHA1 hash, which is used to link every object with another, when the commit references a TREE, it will use the TREE's hash to do so.  
  
This architecture turns out to be very resource efficient, if you create 10 files with the same content "hello world", even if they have different names, you will have a single BLOB representing it, and a tree calling this same BLOB 10 times, saving a lot of space.  
  
If you choose to change a single file's content and commit it, Git would create a new TREE, and a new BLOB, but all the other existing objects, would already exist, therefore it just references the old ones, again, saving a lot of space.



[[Git Storage Pic.jpg]]