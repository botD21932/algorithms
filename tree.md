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

    def isValidBST(self, root: TreeNode) -> bool:
        if(root == None):
            return True
        stack = [(root, float('-inf'), float('inf'))]
        while(stack != []):
            root, lower, upper = stack.pop()
            if(root == None):
                continue
            value = root.val
            if(value <= lower or value >= upper):
                return False
            stack.append((root.right, value, upper))
            stack.append((root.left, lower, value))
        return True

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

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/
