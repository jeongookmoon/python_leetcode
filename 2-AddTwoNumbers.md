# Add Two Numbers
- Given two **non-empty** linked lists representing two non-negative integers
- The digits are stored in **reverse order** and each of their nodes contain a single digit
- Add the two numbers and return it as a linked list

### Note
* Need to return a header node of the linekd list (return list also reverse order)
* No negative case
* Need to take care of carry

## Dictionary Utilization
O(n)
```python
def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
  # Need two pointers; return node and travelling node that will make result list
  traveller = returnNode = ListNode()
  
  # Init carry
  carry = 0

  # loop until l1 or l2 not exist:
  # *case where carry at the end
  while l1 or l2 or carry:
    # set values
    l1_value = l1.val if l1 else 0
    l2_value = l2.val if l2 else 0


    # calculate sum  
    sum = l1_value + l2_value + carry
    # calcualte carry by floor value
    carry = sum // 10
    # calculate one digit of sum for result list
    oneDigitSum = sum % 10


    # make result list
    traveller.next = ListNode(oneDigitSum)


    # move all nodes
    traveller = traveller.next
    # *case of no next 
    l1 = l1.next if l1 else None
    l2 = l2.next if l2 else None
  # return returnNode next since result list starts from next
  return returnNode.next
```