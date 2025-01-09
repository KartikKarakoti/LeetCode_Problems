class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

class Solution:
    def reverseList(self, head, k):
        prev = None
        curr = head
        
        for _ in range(k):
            next_node = curr.next
            curr.next = prev
            prev = curr
            curr = next_node
        
        return prev, curr # Return new head and the next node after k elements

    def reverseKGroup(self, head, k):
        dummy = ListNode(0)
        dummy.next = head
        ptr = dummy
        
        while ptr is not None:
            tracker = ptr
            
            # Check if there are k nodes to reverse
            for _ in range(k):
                tracker = tracker.next
                if tracker is None:
                    return dummy.next # If fewer than k nodes, return result
            
            # Reverse k nodes
            prev, curr = self.reverseList(ptr.next, k)
            
            last_node_of_reversed_group = ptr.next
            last_node_of_reversed_group.next = curr
            ptr.next = prev
            
            ptr = last_node_of_reversed_group # Move ptr forward
        
        return dummy.next
