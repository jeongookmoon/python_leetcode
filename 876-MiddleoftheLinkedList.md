# Middle of the Linked List
- Given a non-empty, singly linked list with head node head, return a middle node of linked list.
- If there are two middle nodes, return the second middle node.

### Note
* Using two pointers; one gets increased by one + the other gets increased by two -> by the time two reaces the end, one is at the middle
* Using array; half of the length is the middle

## Using two pointers
O(n)
```python
def middleNode(head: ListNode) -> ListNode:
  if head is None:
    return head
  try:
    onebyone = head
    twobytwo = head.next
    while twobytwo is not None:
      onebyone = onebyone.next
      twobytwo = twobytwo.next.next
    return onebyone
  except:
    return onebyone
```

## Using a list
O(n)
```python
def middleNode(head: ListNode) -> ListNode:
  listNodes = [head]
  while listNodes[-1].next:
      listNodes.append(listNodes[-1].next)
  return listNodes[int(len(listNodes)/2)]
```