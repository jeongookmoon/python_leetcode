# Invert Binary Tree
- Invert a binary tree.

## Recursion
runtime: O(n), space: O(n)
```python
def invertTree(root: TreeNode) -> TreeNode:
    def dfs(node):
        if node is None:
            return
            
        dfs(node.left)
        dsf(node.right)

        node.left, node.right = node.right, node.left

    dfs(root)
    return root
```