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

    def equalTrees(self, s: TreeNode, t: TreeNode) -> bool:
        if(s == None and t == None):
            return True
        if(s == None or t == None):
            return False
        return (s.val == t.val and self.equalTrees(s.left,t.left) and self.equalTrees(s.right,t.right))
    def isSubtree(self, s: TreeNode, t: TreeNode) -> bool:
        return (s != None and (self.equalTrees(s,t) or self.isSubtree(s.left,t) or self.isSubtree(s.right,t)))

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

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/
