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
        pointA = headA
        pointB = headB
        while(pointA != pointB):
            if not pointA:
                pointA = headB
            else:
                pointA = pointA.next
            if not pointB:
                pointB = headA
            else:
                pointB = pointB.next
        return pointA

## Reorder List

https://leetcode.com/problems/reorder-list/

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

    def hasCycle(self, head: ListNode) -> bool:
        if not head:
            return False
        slowPointer = head
        fastPointer = head.next
        while fastPointer and fastPointer != slowPointer:
            fastPointer = fastPointer.next
            if not fastPointer:
                return False
            slowPointer = slowPointer.next
            fastPointer = fastPointer.next
        if slowPointer == fastPointer:
            return True
        return False

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

    def detectCycle(self, head: ListNode) -> ListNode:
        if not head:
            return None
        slowPointer = head
        fastPointer = head.next
        while(fastPointer and fastPointer != slowPointer):
            fastPointer = fastPointer.next
            if not fastPointer:
                return None
            slowPointer = slowPointer.next
            fastPointer = fastPointer.next
        if(slowPointer == fastPointer):
            current = head
            fastPointer = fastPointer.next
            while(current!=fastPointer):
                current = current.next
                fastPointer = fastPointer.next
            return current
        return None

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

    def middleNode(self, head: ListNode) -> ListNode:
        firstPointer = head
        secondPointer = head
        while secondPointer and secondPointer.next:
            firstPointer = firstPointer.next
            secondPointer = secondPointer.next.next
        return firstPointer

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

    def reverseList(self, head: ListNode) -> ListNode:
        previous = None
        current = head
        while current:
            nextTemp = current.next
            current.next = previous
            previous = current
            current = nextTemp
        return previous
