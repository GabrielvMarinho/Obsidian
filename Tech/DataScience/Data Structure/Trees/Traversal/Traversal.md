Algorithm to visit each node in a [[Binary Tree]] once.


Different Traversals exist for different purposes, if you want to reverse a binary tree, you can use a [[Postorder Traversal]] and [[Preorder Traversal]], but you would never use a [[Inorder Traversal]] for example, because since it goes left -> root -> right, when you go root, it makes the already sorted left to be the right.