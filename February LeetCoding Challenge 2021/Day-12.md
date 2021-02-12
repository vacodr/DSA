# Number of Steps to Reduce a Number to Zero
Given a non-negative integer num, return the number of steps to reduce it to zero. If the current number is even, you have to divide it by 2, otherwise, you have to subtract 1 from it.

Problem type: Easy

Link: https://leetcode.com/problems/number-of-steps-to-reduce-a-number-to-zero/
# Code
```java
class Solution {
    public int numberOfSteps (int num) {
        
        int count=0;
        
       while(num!=0)
       {
           if(num%2==0) num=num/2;
           else num = num-1;
           count++;
       }
        
        return count;
        
    }
}
```
