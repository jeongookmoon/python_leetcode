# Reverse Linked List
- Reverse a singly linked list.

## Loop
O(n)
```python
def reverseList(head: ListNode) -> ListNode:
  prev = None
  
  while head:
    # set current
    current = head
    # move head
    head = head.next
    # reverse order
    current.next = prev
    # save current as prev
    prev = current
    
  return prev
```
