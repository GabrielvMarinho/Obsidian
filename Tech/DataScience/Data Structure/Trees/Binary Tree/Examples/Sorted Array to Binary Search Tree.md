```java
public class TreeNode {
     int val;
     TreeNode left;
     TreeNode right;
     TreeNode() {}
     TreeNode(int val) { this.val = val; }
     TreeNode(int val, TreeNode left, TreeNode right) {
         this.val = val;
         this.left = left;
         this.right = right;
     }
 }

class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        return CreateTreeNode(nums, 0, nums.length-1);
    }  
    public static TreeNode CreateTreeNode(int[] nums, int start, int end){
        if(start>end) return null;
        int mid = start+(end-start)/2;
        TreeNode treeNode = new TreeNode(nums[mid]);
        treeNode.left = CreateTreeNode(nums, start, mid-1);
        treeNode.right = CreateTreeNode(nums, mid+1, end);
        return treeNode;
    }
}
```