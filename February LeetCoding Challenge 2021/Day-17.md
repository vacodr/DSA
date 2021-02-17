#  Container With Most Water
Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate (i, ai). n vertical lines are drawn such that the two endpoints of the line i is at (i, ai) and (i, 0). Find two lines, which, together with the x-axis forms a container, such that the container contains the most water.

Notice that you may not slant the container.

Problem type: Medium

Link: https://leetcode.com/problems/container-with-most-water/
## Code
```java
class Solution {
    public int maxArea(int[] height) {
        
        int start=0;
        int end = height.length-1;
        int c=0;
        
        while(start<end){
            
           c= Math.max(c,(end-start)*Math.min(height[start],height[end]));
            
            if(height[start]<height[end]){
                
                start++;
            }
            else{
                end--;
            }
        }
        
        return c;
        
    }
}
```
