"""
# Definition for a Node.
class Node:
    def __init__(self, val: Optional[int] = None, children: Optional[List['Node']] = None):
        self.val = val
        self.children = children
"""

class Solution:
    def levelOrder(self, root: 'Node') -> List[List[int]]:
        if not root:
            return []
        q = deque([root])
        res = []

        while q:
            new_q = deque()
            level = []
            for node in q:
                level.append(node.val)
                for child in node.children:
                    new_q.append(child)
            
            res.append(level)
            q = new_q
        
        return res
        
