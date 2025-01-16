# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def reverseBetween(self, head: Optional[ListNode], left: int, right: int) -> Optional[ListNode]:
        # If the list is empty or left position is the same as right, return  
        # the original list
        if not head or left == right:
            return head

        # Create a dummy node to handle edge case when left = 1
        dummy = ListNode(0)
        dummy.next = head
        prev = dummy

        # Move prev to the node just before the left position
        for _ in range(left - 1):
            prev = prev.next

        # Current node is the node at the left position
        curr = prev.next

        # Reverse the portion of the linked list between left and right 
        # positions
        for _ in range(right - left):
            next_node = curr.next
            curr.next = next_node.next
            next_node.next = prev.next
            prev.next = next_node

        # Return the updated head of the linked list
        return dummy.next
