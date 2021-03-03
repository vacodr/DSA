# Missing Number
Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

Follow up: Could you implement a solution using only O(1) extra space complexity and O(n) runtime complexity?

Problem type: Easy

Link: https://leetcode.com/problems/missing-number/
## Code
```java
class Solution {
    public int missingNumber(int[] nums) {
        
        Set<Integer> s= new HashSet<>();       
        int len=nums.length;
        int sum= len*(len+1)/2;
        int actsum=0;
        
        for(int i: nums){   
           actsum+=i; 
        }
        return sum-actsum;        
    }
}
```
