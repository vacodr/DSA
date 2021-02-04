# 594. Longest Harmonious Subsequence
We define a harmonious array as an array where the difference between its maximum value and its minimum value is exactly 1.

Given an integer array nums, return the length of its longest harmonious subsequence among all its possible subsequences.

A subsequence of array is a sequence that can be derived from the array by deleting some or no elements without changing the order of the remaining elements.

Problem type: Easy

link: https://leetcode.com/problems/longest-harmonious-subsequence/
## Code
```java
class Solution {
    public int findLHS(int[] nums) {
        
        int res=0;
       Map<Integer,Integer> map= new HashMap<>();
        
        for(int i:nums)
              map.put(i, map.getOrDefault(i, 0) + 1);
        
        for(int j:map.keySet()){
            
            if(map.containsKey(j+1))
            {
                res=Math.max(res,map.get(j)+map.get(j+1));
                
            }   
        }
        
        return res;
        
    }
}
```
