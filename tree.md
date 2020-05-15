# Tree

+ [Binary Search Tree Iterator](#binary-search-tree-iterator)
+ [Validate Binary Search Tree](#validate-binary-search-tree)
+ [Kth Smallest Element in a BST](#kth-smallest-element-in-a-bst)
+ [Subtree of Another Tree](#subtree-of-another-tree)
+ [Binary Tree Level Order Traversal](#binary-tree-level-order-traversal)
+ [Path Sum](#path-sum)
+ [Invert Binary Tree](#invert-binary-tree)
+ [Same Tree](#same-tree)
+ [Maximum Depth of Binary Tree](#maximum-depth-of-binary-tree)
+ [Symmetric Tree](#symmetric-tree)
+ [Binary Tree Inorder Traversal](#binary-tree-inorder-traversal)

## Binary Search Tree Iterator

https://leetcode.com/problems/binary-search-tree-iterator/

## Validate Binary Search Tree

https://leetcode.com/problems/validate-binary-search-tree/

## Kth Smallest Element in a BST

https://leetcode.com/problems/kth-smallest-element-in-a-bst/

## Subtree of Another Tree

https://leetcode.com/problems/subtree-of-another-tree/

## Binary Tree Level Order Traversal

https://leetcode.com/problems/binary-tree-level-order-traversal/

## Path Sum

https://leetcode.com/problems/path-sum/

## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/

## Same Tree

https://leetcode.com/problems/same-tree/

## Maximum Depth of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree/

## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/

    def isMirror(self, root1: TreeNode, root2: TreeNode) -> bool:
        if(root1 == None and root2 == None):
            return True
        if(root1 == None or root2 == None):
            return False
        return (root1.val == root2.val and self.isMirror(root1.right, root2.left) and self.isMirror(root1.left, root2.right))
    def isSymmetric(self, root: TreeNode) -> bool:
        return self.isMirror(root,root)

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/
