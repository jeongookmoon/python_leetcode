# Minimum Depth of Binary Tree
- Given a binary tree, find its minimum depth
- The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node

## Iteration: BFS + Deque
Runtime: O(n), Space: O(n)
```python
def minDepth(root: TreeNode) -> int:
    if root is None:
        return 0
    deque = collections.deque([(root, 1)])
    while deque:
        node, level = deque.popleft()
        if node is None:
            continue
        if node.left is None and node.right is None:
            return level
        deque.append((node.left, level+1))
        deque.append((node.right, level+1))
```
