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

    def isPalindrome(self, head: ListNode) -> bool:
        list = []
        while head:
            list.append(head.val)
            head = head.next
        for i in range(0, int(len(list)/2)):
            if (list[i] != list[len(list) - i - 1]):
                return False
        return True

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/
