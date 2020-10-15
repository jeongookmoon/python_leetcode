# Same Tree
- Given two binary trees, write a function to check if they are the same or not.
- Two binary trees are considered the same if they are structurally identical and the nodes have the same value.

## Iteration
Runtime: O(n), Space: O(n)
```python
def isSameTree(p: TreeNode, q: TreeNode) -> bool:
    stack = [(p, q)]
    while stack:
        one, another = stack.pop()
        if not one and not another:
            continue
        elif not one or not another or one.val != another.val:
            return False
        stack.extend([(one.left, another.left), (one.right, another.right)])
    return True
```