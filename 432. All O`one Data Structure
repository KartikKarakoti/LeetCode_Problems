class Node:
    def __init__(self, freq):
        self.freq = freq
        self.keys = set()
        self.prev = None
        self.next = None


class AllOne:
    def __init__(self):
        # Initialize the doubly linked list with dummy head and tail
        self.head = Node(0)
        self.tail = Node(0)
        self.head.next = self.tail
        self.tail.prev = self.head
        self.key_node_map = {}  # Maps keys to their corresponding node

    def _add_node(self, prev_node, freq):
        """Add a new node with given frequency after the prev_node."""
        new_node = Node(freq)
        new_node.prev = prev_node
        new_node.next = prev_node.next
        prev_node.next.prev = new_node
        prev_node.next = new_node
        return new_node

    def _remove_node_if_empty(self, node):
        """Remove the node if it has no keys."""
        if not node.keys:
            node.prev.next = node.next
            node.next.prev = node.prev

    def inc(self, key: str) -> None:
        if key in self.key_node_map:
            current_node = self.key_node_map[key]
            current_node.keys.remove(key)

            next_freq = current_node.freq + 1
            next_node = current_node.next

            # If the next node doesn't exist or doesn't have the right frequency, create it
            if next_node == self.tail or next_node.freq != next_freq:
                next_node = self._add_node(current_node, next_freq)

            next_node.keys.add(key)
            self.key_node_map[key] = next_node

            # Remove the current node if empty
            self._remove_node_if_empty(current_node)
        else:
            # If key is new, add it to the first node (freq=1) or create it
            first_node = self.head.next
            if first_node == self.tail or first_node.freq != 1:
                first_node = self._add_node(self.head, 1)
            first_node.keys.add(key)
            self.key_node_map[key] = first_node

    def dec(self, key: str) -> None:
        if key not in self.key_node_map:
            return

        current_node = self.key_node_map[key]
        current_node.keys.remove(key)

        if current_node.freq == 1:
            # If the frequency is 1, remove the key entirely
            del self.key_node_map[key]
        else:
            prev_freq = current_node.freq - 1
            prev_node = current_node.prev

            # If the previous node doesn't exist or doesn't have the right frequency, create it
            if prev_node == self.head or prev_node.freq != prev_freq:
                prev_node = self._add_node(current_node.prev, prev_freq)

            prev_node.keys.add(key)
            self.key_node_map[key] = prev_node

        # Remove the current node if empty
        self._remove_node_if_empty(current_node)

    def getMaxKey(self) -> str:
        if self.tail.prev == self.head:
            return ""
        return next(iter(self.tail.prev.keys))  # Get any key from the max frequency node

    def getMinKey(self) -> str:
        if self.head.next == self.tail:
            return ""
        return next(iter(self.head.next.keys))  # Get any key from the min frequency node


# Your AllOne object will be instantiated and called as such:
# obj = AllOne()
# obj.inc(key)
# obj.dec(key)
# param_3 = obj.getMaxKey()
# param_4 = obj.getMinKey()
