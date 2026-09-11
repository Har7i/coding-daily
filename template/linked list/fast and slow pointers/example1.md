Example 1: Given the head of a linked list with an odd number of nodes head, return the value of the node in the middle.
For example, given a linked list that represents 1 -> 2 -> 3 -> 4 -> 5, return 3.

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class solution:
    def example1(self, head):
        slow = fast = head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        return slow.val
