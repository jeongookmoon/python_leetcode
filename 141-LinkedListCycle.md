# Linked List Cycle
- Given head, the head of a linked list, determine if the linked list has a cycle in it.
- There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.
- Return true if there is a cycle in the linked list. Otherwise, return false.

### Note
* Using set, check passed list node
* Using two pointers; pointerA: increase by one, pointerB: increase by two
* If cycle exists, pointerA and pointerB will meet.

## Using Set
O(n)
```python
def hasCycle(head: ListNode) -> bool:
  seen = set()
  while head is not None:
    if head in seen:
      return True
    else:
      seen.add(head)
    head = head.next
  return False
```

## Using Pointers
O(n)
```python
def hasCycle(head: ListNode) -> bool:
  onebyone, twobytwo = head, head
  try:
    while onebyone is not None or twobytwo is not None:
      onebyone = onebyone.next
      twobytwo = twobytwo.next.next
      if onebyone == twobytwo:
        return True
    return False
  except:
    return False
```