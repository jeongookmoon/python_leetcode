# Remove Linked List Elements
- Remove all elements from a linked list of integers that have value val.

## Dictionary Utilization
O(n)
```python
def removeElements(head: ListNode, val: int) -> ListNode:
    updater = returnNode = ListNode()
    updater.next = head
    returnNode.next = head

    while updater.next is not None:
      if updater.next.val == val:
          updater.next = updater.next.next
      else:
          updater = updater.next
    
    return returnNode.next
```