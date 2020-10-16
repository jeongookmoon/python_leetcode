# Path Sum
- Given a binary tree and a sum, determine if the tree has a root-to-leaf path such that adding up all the values along the path equals the given sum.
- Note: A leaf is a node with no children.

## Recursion
Runtime: O(n), Space: O(n)
```python
class Solution:
    def hasPathSum(self, root: TreeNode, sum: int) -> bool:
        # Reaching the last one's left or right
        if not root:
            return False
        # Reaching the last one and found path that matches sum
        elif not (root.left or root.right) and root.val == sum:
            return True
        sum -= root.val
        return self.hasPathSum(root.left, sum) or self.hasPathSum(root.right, sum)
```