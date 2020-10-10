# Merge Two Sorted Lists
- Merge two sorted linked lists and return it as a new sorted list. The new list should be made by splicing together the nodes of the first two lists.

## Loop
O(n)
```python
def mergeTwoLists(l1: ListNode, l2: ListNode) -> ListNode:
  result = updater = ListNode()
  
  while l1 or l2:
      if l1 is None:
          updater.next = ListNode(l2.val)
          l2 = l2.next
          
      elif l2 is None:
          updater.next = ListNode(l1.val)
          l1 = l1.next

      else:
          if l1.val > l2.val:
              updater.next = ListNode(l2.val)
              l2 = l2.next
          else:
              updater.next = ListNode(l1.val)
              l1 = l1.next
      updater = updater.next
  
  return result.next
```
