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

```python
def reorderList(self, head: ListNode) -> None:
    if not head:
        return head
    nodeList = []
    currentNode = head
    begin = 0
    end = -1
    while currentNode:
        nodeList.append(currentNode)
        currentNode = currentNode.next
        end = end + 1
    while begin < end:
        nodeList[begin].next = nodeList[end]
        begin = begin + 1
        if begin >= end:
            break
        nodeList[end].next = nodeList[begin]
        end = end - 1
    nodeList[end].next = None


def reorderList(self, head: ListNode) -> None:
    if not head:
        return head
    fastPoint = head
    slowPoint = head
    while fastPoint and fastPoint.next:
        slowPoint = slowPoint.next
        fastPoint = fastPoint.next.next
    tail = slowPoint
    previous = None
    half = slowPoint.next
    while half:
        slowPoint.next = previous
        previous = slowPoint
        slowPoint = half
        half = half.next
    slowPoint.next = previous
    current = None
    while current != tail:
        current = head.next
        head.next = slowPoint
        head = slowPoint
        slowPoint = current

```

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

    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        start = ListNode(0)
        start.next = head
        firstPoint = start
        secondPoint = start
        for i in range(1,n+2):
            firstPoint = firstPoint.next
        while firstPoint:
            firstPoint = firstPoint.next
            secondPoint = secondPoint.next
        secondPoint.next = secondPoint.next.next
        return start.next

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
