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

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    head = ListNode(0)
    pointer = head
    while l1 and l2:
        if l1.val < l2.val:
            pointer.next = l1
            l1 = l1.next
        else:
            pointer.next = l2
            l2 = l2.next
        pointer = pointer.next
    if not l1:
        pointer.next = l2
    elif not l2:
        pointer.next = l1
    return head.next


def middleNode(self, head: ListNode) -> ListNode:
    firstPoint = head
    secondPoint = head
    while secondPoint.next and secondPoint.next.next:
        firstPoint = firstPoint.next
        secondPoint = secondPoint.next.next
    return firstPoint


def sortList(self, head: ListNode) -> ListNode:
    if not head or not head.next:
        return head
    middle = self.middleNode(head)
    rightList = self.sortList(middle.next)
    middle.next = None
    leftList = self.sortList(head)
    return self.mergeTwoLists(leftList, rightList)

```

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

```python
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

```

## Reorder List

https://leetcode.com/problems/reorder-list/

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

```python
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

```

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

```python
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
        while(current != fastPointer):
            current = current.next
            fastPointer = fastPointer.next
        return current
    return None

```

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
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

```

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    previous = None
    current = head
    while current:
        nextTemp = current.next
        current.next = previous
        previous = current
        current = nextTemp
    return previous


def isEqual(self, firstHalf: ListNode, secondHalf: ListNode) -> bool:
    while secondHalf:
        if secondHalf.val != firstHalf.val:
            return False
        secondHalf = secondHalf.next
        firstHalf = firstHalf.next
    return True


def isPalindrome(self, head: ListNode) -> bool:
    if not head or not head.next:
        return True
    firstPoint = head
    secondPoint = head
    while secondPoint.next and secondPoint.next.next:
        firstPoint = firstPoint.next
        secondPoint = secondPoint.next.next
    if not secondPoint.next:
        secondHalf = copy.copy(firstPoint)
    else:
        secondHalf = copy.copy(firstPoint.next)
    firstPoint.next = None
    firstHalf = self.reverseList(head)
    return self.isEqual(firstHalf, secondHalf)

```

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

```python
def middleNode(self, head: ListNode) -> ListNode:
    firstPointer = head
    secondPointer = head
    while secondPointer and secondPointer.next:
        firstPointer = firstPointer.next
        secondPointer = secondPointer.next.next
    return firstPointer

```

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    previous = None
    current = head
    while current:
        nextTemp = current.next
        current.next = previous
        previous = current
        current = nextTemp
    return previous

```
