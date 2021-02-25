# Shortest Unsorted Continuous Subarray
Given an integer array nums, you need to find one continuous subarray that if you only sort this subarray in ascending order, then the whole array will be sorted in ascending order.

Return the shortest such subarray and output its length.

Problem type: Medium

Link: https://leetcode.com/problems/shortest-unsorted-continuous-subarray/
## Code
```java
class Solution {

    public int findUnsortedSubarray(int[] nums) {
        Stack<Integer> st = new Stack<>();
        int left  = nums.length-1;

        for(int i=0; i< nums.length;){
            if(st.empty()){
                st.push(i);
                i++;
            } else{
                if(nums[st.peek()] > nums[i]){
                    left = Math.min(left, st.peek());
                    st.pop();
                } else{
                    st.push(i);
                    i++;
                }
            }
        }

        st.clear();
        int right = 0;


        for(int i=nums.length-1;i>=0;){
            if(st.empty()){
                st.push(i);
                i--;
            } else{
                if(nums[st.peek()] < nums[i]){
                    right = Math.max(right, st.peek());
                    st.pop();
                } else{
                    st.push(i);
                    i--;
                }
            }
        }

        if(left >= right){
            return 0;
        } else{
            return right- left +1;
        }

    }
}
```
