# Arithmetic Slices
A sequence of numbers is called arithmetic if it consists of at least three elements and if the difference between any two consecutive elements is the same.

Problem type: Medium

Link:https://leetcode.com/problems/arithmetic-slices/
## Code
```java
class Solution {
    public int numberOfArithmeticSlices(int[] A) {
        
        int current=0,sum=0;
        
        for(int i=2;i<A.length;i++){
    
            if(A[i]-A[i-1]==A[i-1]-A[i-2]){
                
                current+=1;
                sum+=current;
            }
            else{
                current=0;
            }
        }
        
        return sum;
        
    }
}
```
