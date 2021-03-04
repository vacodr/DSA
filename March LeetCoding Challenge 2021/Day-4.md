# Intersection of Two Linked Lists
Write a program to find the node at which the intersection of two singly linked lists begins.

Problem type: Easy

Link: https://leetcode.com/problems/intersection-of-two-linked-lists/

## Code
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */

public class Solution {
     public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        ListNode a = headA;
        ListNode b = headB;

        while(a!=b){
            if(a == null){
                a = headB;
            } else{
                a = a.next;
            }


            if(b == null){
                b = headA;
            } else{
                b = b.next;
            }
        }

        return a;

    }
}

```
