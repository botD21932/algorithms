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

    def sortList(self, head: ListNode) -> ListNode:
        if(head == None or head.next == None):
            return head
        slowWave = head
        fastWave = head
        while(fastWave.next != None and fastWave.next.next != None):
            slowWave = slowWave.next
            fastWave = fastWave.next.next
        rightList = self.sortList(slowWave.next)
        slowWave.next = None
        leftList = self.sortList(head)
        result = ListNode(None)
        previous = result
        while(leftList != None and rightList != None):
            if leftList.val < rightList.val:
                previous.next = leftList
                previous = leftList
                leftList = leftList.next
            else:
                previous.next = rightList
                previous = rightList
                rightList = rightList.next
        if(leftList != None):
            previous.next = leftList
        elif(rightList != None):
            previous.next = rightList
        return result.next

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

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
