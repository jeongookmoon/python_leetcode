# Average of Levels in Binary Tree
- Given a non-empty binary tree, return the average value of the nodes on each level in the form of an array.

## Iteration
runtime: O(n) , space: O(n)
```python
def averageOfLevels(root: TreeNode) -> List[float]:
    if root is None:
      return None
    
    result = []
    current_level = [root]

    while current_level:
      nodes = []
      next_level = []

      for node in current_level:
        nodes.append(node.val)
        if node.left:
          next_level.append(node.left)
        if node.right:
          next_level.append(node.right)
      
      result.append(sum(nodes)/len(nodes))
      current_level = next_level
    
    return result
```
