# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
from collections import deque
class Solution:
    def levelOrderBottom(self, root: Optional[TreeNode]) -> List[List[int]]:
        if root is None:
            return []
        jk=deque([root])
        res=[]
        while jk:
            l=[]
            for _ in range(len(jk)):
                node=jk.popleft()
                l.append(node.val)
                if node.left:
                    jk.append(node.left)
                if node.right:
                    jk.append(node.right)
            res.append(l)
        return res[::-1]                    
