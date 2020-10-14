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

## Iteration
runtime: O(n), space: O(n)
```python
def invertTree(root: TreeNode) -> TreeNode:
    stack = [root]
    
    while stack:
      updater = stack.pop()
      if updater:
          updater.left, updater.right = updater.right, updater.left
          stack.extend(updater.left, updater.right)
    
    return root
```