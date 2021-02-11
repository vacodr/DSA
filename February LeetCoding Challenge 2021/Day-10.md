# 138. Copy List with Random Pointer
A linked list of length n is given such that each node contains an additional random pointer, which could point to any node in the list, or null.

Construct a deep copy of the list. The deep copy should consist of exactly n brand new nodes, where each new node has its value set to the value of its corresponding original node. Both the next and random pointer of the new nodes should point to new nodes in the copied list such that the pointers in the original list and copied list represent the same list state. None of the pointers in the new list should point to nodes in the original list.

For example, if there are two nodes X and Y in the original list, where X.random --> Y, then for the corresponding two nodes x and y in the copied list, x.random --> y.

Return the head of the copied linked list.

The linked list is represented in the input/output as a list of n nodes. Each node is represented as a pair of [val, random_index] where:

val: an integer representing Node.val
random_index: the index of the node (range from 0 to n-1) that the random pointer points to, or null if it does not point to any node.
Your code will only be given the head of the original linked list.

Problem type: Medium

Link: https://leetcode.com/problems/copy-list-with-random-pointer/
# Code
```java
class Solution {

    // TC : O(n)
    // SC : O(n)
    public Node copyRandomList(Node head) {
        if(head == null){
            return null;
        }

        // duplicate nodes
        Node it = head;
        while(it!=null){
            Node nextIt = it.next;
            Node newNode = new Node(it.val);
            newNode.next = it.next;
            it.next = newNode;
            it = nextIt;
        }

        // set random pointer

        Node newIt = head.next;
        Node newHead = head.next;
        it = head;

        while(it!=null){
            if(it.random!=null) {
                newIt.random = it.random.next;

            }
            it = newIt.next;
            if(it!=null)
                newIt = it.next;
        }

        // Reseting the next nodes so as to separte old and  duplicate lists

        it = head;
        newIt = head.next;

        while(it!=null){
            it.next = newIt.next;
            it = it.next;
            if(it!=null){
                newIt.next = it.next;
                newIt = it.next;
            }
        }

        return newHead;

    }
}
```
