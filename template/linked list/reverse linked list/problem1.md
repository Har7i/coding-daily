Reverse Linked List II

Solution
Given the head of a singly linked list and two integers left and right where left <= right, reverse the nodes of the list from position left to position right, and return the reversed list.

 

Example 1:


Input: head = [1,2,3,4,5], left = 2, right = 4
Output: [1,4,3,2,5]
Example 2:

Input: head = [5], left = 1, right = 1
Output: [5]
 
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
    
class solution:
    def problem1(self, head, left, right):
        dummy = ListNode(0, head)
        prev = dummy
        for _ in range(left - 1):
            prev = prev.next
        head = prev.next
        for _ in range(right - left):
            hnext = head.next
            head.next = hnext.next
            hnext.next = prev.next
            prev.next = hnext
        return dummy.next