In a linked list of size n, where n is even, the ith node (0-indexed) of the linked list is known as the twin of the (n-1-i)th node, if 0 <= i <= (n / 2) - 1.

For example, if n = 4, then node 0 is the twin of node 3, and node 1 is the twin of node 2. These are the only nodes with twins for n = 4.
The twin sum is defined as the sum of a node and its twin.

Given the head of a linked list with even length, return the maximum twin sum of the linked list.

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = None
    
class solution:
    def example2(self, head):
        def findmid(head):
            slow = head
            fast = head.next
            while fast and fast.next:
                slow = slow.next
                fast = fast.next.next
            return slow
        
        def reverse(head):
            dummy = ListNode(0, head)
            while head and head.next:
                hnext = head.next
                head.next = hnext.next
                hnext.next = dummy.next
                dummy.next = hnext
            return dummy.next

        first_tail = findmid(head)
        second_head = reverse(first_tail.next)
        first_tail.next = None
        slow, fast = head, second_head
        res = 0
        while slow and fast:
            res = max(res, slow.val + fast.val)
            slow, fast = slow.next, fast.next
        return res