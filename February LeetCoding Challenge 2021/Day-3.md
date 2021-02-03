# 141. Linked List Cycle
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.

Problem typr: Easy

link: https://leetcode.com/problems/linked-list-cycle/
## Code
```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public boolean hasCycle(ListNode head) {
        
        if(head==null) return false;
        ListNode p=head;
        ListNode q= head;
        
       
        while(true){
            
            p= p.next;
            
            if(q.next!=null) q=q.next.next;
            
            else return false;
            
            if(p==null || q==null) return false;
            
            if(p==q) return true;
        }       
    }
}
```
