# Diameter-of-Binary-Tree
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        if root is None:
            return 0
        r=[0]
        def path(root):
            if root is None:
                return 0
            left=path(root.left)
            right=path(root.right)
            r[0]=max(r[0],left+right)
            return max(left,right)+1
        path(root)
        return r[0]
