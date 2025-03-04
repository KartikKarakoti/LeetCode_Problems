class ListNode:
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.next = None
class MyHashMap:

    def __init__(self):
        self.size = 1000
        self.hash_table = [None] * self.size 

    def put(self, key: int, value: int) -> None:
        index = key % self.size 
    
        if self.hash_table[index] == None:
            # We do not have anything in this bin, just create a new node 
            self.hash_table[index] = ListNode(key, value)
        else:
            # We do have something in this bin, traverse it checking to see if we have a matching key. If not just append a node to the end of the bin
            curr_node = self.hash_table[index]
            while True:
                if curr_node.key == key:
                    curr_node.value = value
                    return 
                if curr_node.next == None: break
                curr_node = curr_node.next 
            # Did not find a matching key here, so append a key, value pair in this bin
            curr_node.next = ListNode(key, value)

    def get(self, key: int) -> int:
        index = key % self.size 
        
        curr_node = self.hash_table[index]
        
        while curr_node:
            if curr_node.key == key:
                return curr_node.value 
            else:
                curr_node = curr_node.next
        
        return -1
        

    def remove(self, key: int) -> None:
        index = key % self.size 
        
        curr_node = prev_node = self.hash_table[index]
        
         # Removing from empty bin just return
        if not curr_node: return 
        
        if curr_node.key == key:
            # We found the node to delete immediately, we can now skip over it 
            self.hash_table[index] = curr_node.next
        else:
            # We did not find the node to delete we must now traverse the bin
            curr_node = curr_node.next
            
            while curr_node:
                if curr_node.key == key:
                    prev_node.next = curr_node.next 
                    break
                else:
                    prev_node, curr_node = prev_node.next, curr_node.next
        


# Your MyHashMap object will be instantiated and called as such:
# obj = MyHashMap()
# obj.put(key,value)
# param_2 = obj.get(key)
# obj.remove(key)
