Sorted [[List]] to [[Binary Search Tree]]

```java
class Solution {
    public TreeNode sortedListToBST(ListNode head) {
        if (head == null) return null;
        if (head.next == null) return new TreeNode(head.val);

        ListNode prev = null;
        ListNode slow = head;
        ListNode fast = head;

        // Find the middle (slow will be mid)
        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }

        // Disconnect the left half from mid
        if (prev != null) {
            prev.next = null;
        }

        TreeNode root = new TreeNode(slow.val);

        // Left subtree → only if slow isn't head
        if (slow != head) {
            root.left = sortedListToBST(head);
        }

        root.right = sortedListToBST(slow.next);

        return root;
    }
}
```