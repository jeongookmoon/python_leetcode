# Remove Duplicates from Sorted List
- Given a sorted linked list, delete all duplicates such that each element appear only once.

## Skip Duplicate ListNode
O(n)
```python
def deleteDuplicates(head: ListNode) -> ListNode:
  updater = head
  while updater and updater.next:
    if updater.val == updater.next.val:
      updater.next = updater.next.next
    else:
      updater = updater.next
  return head
```