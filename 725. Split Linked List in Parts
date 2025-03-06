class Solution:
    def splitListToParts(self, head: Optional[ListNode], k: int) -> List[Optional[ListNode]]:
        # Step 1: Count the number of nodes
        current = head
        count = 0
        while current:
            count += 1
            current = current.next
        
        # Step 2: Calculate the size of each part and the number of extra nodes
        part_size, extra_nodes = divmod(count, k)
        
        # Step 3: Split the list into k parts
        current = head
        result = []
        for i in range(k):
            part_head = current
            for j in range(part_size - 1 + (i < extra_nodes)):
                if current:
                    current = current.next
            if current:
                next_node = current.next
                current.next = None
                current = next_node
            result.append(part_head)
        
        return result
        
