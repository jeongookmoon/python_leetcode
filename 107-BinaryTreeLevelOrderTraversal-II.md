# Binary Tree Level Order Traversal II
- Given a binary tree, return the bottom-up level order traversal of its nodes' values. (ie, from left to right, level by level from leaf to root).

## Iteration: DFS + Stack
Runtime: O(n), Space: O(n)
```python
def levelOrderBottom(root: TreeNode) -> List[List[int]]:
    stack = [(root, 1)]
    result = []
    while stack:
        currentNode, level = stack.pop()
        if currentNode:
            if len(result) < level:
                result.insert(0, [])
            result[-level].append(currentNode.val)
            stack.append([currentNode.left, level+1])
            stack.append([currentNode.right, level+1])
            # print('result {}'.format(result))
            # print('stack {}'.format(stack))
    return result
```

## Iteration: BFS + Deque
Runtime: O(n), Space: O(n)
```python
        deque = collections.deque([(root, 1)])
        result = []
        
        while deque:
            currentNode, level = deque.popleft()
            if currentNode:
                if len(result) < level:
                    result.insert(0, [])
                result[-level].append(currentNode.val)
                if currentNode.left:
                    deque.append((currentNode.left, level+1))
                if currentNode.right:
                    deque.append((currentNode.right, level+1))

        return result
```