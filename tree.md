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
        if not root:
            return True
        stack = [(root, float('-inf'), float('inf'))]
        while stack:
            root, lower, upper = stack.pop()
            if not root:
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

    def hasPathSum(self, root: TreeNode, sum: int) -> bool:
        if not root:
            return False
        elif(not root.left and not root.right and sum - root.val == 0):
            return True
        elif(not root.left and not root.right and sum - root.val != 0):
            return False
        else:
            return self.hasPathSum(root.right, sum - root.val) or self.hasPathSum(root.left, sum - root.val)

## Invert Binary Tree

https://leetcode.com/problems/invert-binary-tree/

    def invertTree(self, root: TreeNode) -> TreeNode:
        if(root == None):
            return None
        right = self.invertTree(root.right)
        left = self.invertTree(root.left)
        root.left = right
        root.right = left
        return root

## Same Tree

https://leetcode.com/problems/same-tree/

    def isSameTree(self, p: TreeNode, q: TreeNode) -> bool:
        if(p == None and q == None):
            return True
        elif(p == None or q == None):
            return False
        elif(p.val != q.val):
            return False
        else:
            return (self.isSameTree(p.left,q.left) and self.isSameTree(p.right,q.right))

## Maximum Depth of Binary Tree

https://leetcode.com/problems/maximum-depth-of-binary-tree/

    def maxDepth(self, root: TreeNode) -> int:
        if(root == None):
            return 0
        else:
            return (1 + max(self.maxDepth(root.left), self.maxDepth(root.right)))

## Symmetric Tree

https://leetcode.com/problems/symmetric-tree/

## Binary Tree Inorder Traversal

https://leetcode.com/problems/binary-tree-inorder-traversal/

    def inorderTraversal(self, root: TreeNode) -> List[int]:
        stack = []
        list = []
        currentNode = root
        while not currentNode or not stack:
            while currentNode:
                stack.append(currentNode)
                currentNode = currentNode.left
            currentNode = stack.pop()
            list.append(currentNode.val)
            currentNode = currentNode.right
        return list
