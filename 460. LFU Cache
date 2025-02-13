class ListNode:
    def __init__(self, key, val):
        self.key = key
        self.val = val
        self.next = self.prev = None

class LFUCache:

    def __init__(self, capacity: int):
        self.cap = capacity

        def initList():
            root = ListNode(-1, -1)
            root.next = root.prev = root
            return root
        self.freq2node = defaultdict(initList)
        self.key2node = {}
        self.key2freq = defaultdict(lambda: 1)
        self.min = 1

    def _insertAfter(self, target, node):
        node.prev = target
        node.next = target.next
        node.next.prev = node
        node.prev.next = node

    def _remove(self, node):
        node.prev.next = node.next
        node.next.prev = node.prev
        node.next = node.prev = None

    def get(self, key: int) -> int:
        if key not in self.key2node: return -1

        node = self.key2node[key]
        val = node.val
        
        freq = self.key2freq[key]
        self.key2freq[key] = freq + 1
        
        self._remove(node)
        self._insertAfter(self.freq2node[freq+1], node)
        
        if self.freq2node[self.min].next.key == -1:
            self.min = freq+1
        
        return val

    def put(self, key: int, value: int) -> None:
        if self.cap == 0: return
        if key in self.key2node:
            node = self.key2node[key]
            node.val = value
            
            freq = self.key2freq[key]
            self.key2freq[key] = freq+1
            self._remove(node)
            self._insertAfter(self.freq2node[freq+1], node)
            if self.freq2node[self.min].next.key == -1:
                self.min = freq+1
            return

        node = ListNode(key, value)
        if len(self.key2node) ==  self.cap:
            lru = self.freq2node[self.min].prev
            self._remove(lru)
            del self.key2node[lru.key]
            del self.key2freq[lru.key]

        self.key2node[key] = node
        self.key2freq[key] = 1
        self._insertAfter(self.freq2node[1], node)
        self.min = 1
