class Solution:
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        fast, slow = head, head
        while(fast and fast.next):
            fast = fast.next.next
            slow = slow.next
            if(fast == slow):
                slow = head
                while(slow is not fast):
                    fast = fast.next
                    slow = slow.next
                return slow
        return None
