# Validate Stack Sequences
Given two sequences pushed and popped with distinct values, return true if and only if this could have been the result of a sequence of push and pop operations on an initially empty stack.

Problem type: Medium

Link: https://leetcode.com/problems/validate-stack-sequences/
## Code
```java
class Solution {

    public boolean validateStackSequences(int[] pushed, int[] popped) {
        Stack<Integer> st= new Stack<>();
        int s = 0;
        for(int i=0;i<pushed.length;i++){
            st.push(pushed[i]);
            while(!st.empty() && popped[s] ==st.peek()){
                st.pop();
                s++;
            }
        }
        return st.empty();
    }
}
```
