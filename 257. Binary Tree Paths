# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def binaryTreePaths(self, root: Optional[TreeNode]) -> List[str]:
        res = []
        def dfs(node,path):
            if not node:
                return 
            
            if path:
                path += "->" + str(node.val)
            else:
                path = str(node.val)

            if not node.left and not node.right:
                res.append(path)
                return 
            dfs(node.right,path)
            dfs(node.left,path)
        
        dfs(root,"")
        return res
