Example: 24. Swap Nodes in Pairs
Given the head of a linked list, swap every pair of nodes. For example, given a linked list 1 -> 2 -> 3 -> 4 -> 5 -> 6, return a linked list 2 -> 1 -> 4 -> 3 -> 6 -> 5.

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class solution:
    def example1(self, head):
    dummy = ListNode(0, head)
    prev = dummy
    while head and head.next:
        hnext = head.next
        head.next = hnext.next
        hnext.next = prev.next
        prev.next = hnext
        prev = head
        head = head.next
    return dummy.next
    