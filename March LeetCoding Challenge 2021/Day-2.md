# Set Mismatch
You have a set of integers s, which originally contains all the numbers from 1 to n. Unfortunately, due to some error, one of the numbers in s got duplicated to another number in the set, which results in repetition of one number and loss of another number.

You are given an integer array nums representing the data status of this set after the error.

Find the number that occurs twice and the number that is missing and return them in the form of an array.

Problem type: Easy

Link: https://leetcode.com/problems/set-mismatch/
## Code
```java
class Solution {
    public int[] findErrorNums(int[] nums) {
        
        Set<Integer> s = new HashSet<>();
        
        int arr[] = new int[2];
        
        for(int i:nums){
            
            if(s.contains(i)){
                
                arr[0]=i;
            }
            
            s.add(i);
        }
        
        for(int j=1;j<=nums.length;j++){
            
            if(!s.contains(j)){
               
                arr[1]=j;
                break;         
            } 
        }
         return arr;
        
    }
}
```
