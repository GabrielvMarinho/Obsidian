[[Traversal]] algorithm.

Left → Root → Right

```
    A
   / \
  B   C
 / \ / \
 D E F G
```
output: D → B → E → A → F → C → G



```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def inorder_traversal(root):
    result = []
    
    def traverse(node):
        if not node:
            return
        traverse(node.left)       # Visit left subtree
        result.append(node.val)   # Visit root
        traverse(node.right)      # Visit right subtree
    
    traverse(root)
    return result
```