# Linked-list

+ [Sort List](#sort-list)
+ [Intersection of Two Linked Lists](#intersection-of-two-linked-lists)
+ [Reorder List](#reorder-list)
+ [Linked List Cycle](#linked-list-cycle)
+ [Linked List Cycle II](#linked-list-cycle-ii)
+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
+ [Merge Two Sorted Lists](#merge-two-sorted-list)
+ [Palindrome Linked List](#palindrome-linked-list)
+ [Middle of the Linked List](#middle-of-the-linked-list)
+ [Reverse Linked List](#reverse-linked-list)

## Sort List

https://leetcode.com/problems/sort-list/

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

    def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
        len1 = 0
        pointA= headA
        while(pointA != None):
            pointA = pointA.next
            len1 = len1 + 1
        len2 = 0
        pointB = headB
        while(pointB != None):
            pointB = pointB.next
            len2 = len2 + 1
        pointA = headA
        pointB = headB
        if(len1<=len2):
            for i in range(len2-len1):
                pointB = pointB.next
        if(len2<len1):
            for i in range(len1-len2):
                pointA = pointA.next
        while(pointA != None):
            if(pointA == pointB):
                return pointA
            pointA = pointA.next
            pointB = pointB.next
        return None

## Reorder List

https://leetcode.com/problems/reorder-list/

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/
