# Maximum Depth of Binary Tree
- Given a binary tree, find its maximum depth.
- The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.
- Note: A leaf is a node with no children.

## Recursion
Runtime: O(n), Space: O(n)
```python
class Solution:
    def maxDepth(self, root: TreeNode) -> int:
    if not root:
      return 0
    return 1 + max(self.maxDepth(TreeNode.left), self.maxDepth(TreeNode.right))
```