class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        result = []
        
        def traverse(node):
            if node:
                # Visit left subtree
                traverse(node.left)
                # Visit right subtree
                traverse(node.right)
                # Visit node itself
                result.append(node.val)
        
        traverse(root)
        return result
        
