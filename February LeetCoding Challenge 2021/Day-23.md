# Search a 2D Matrix II
Write an efficient algorithm that searches for a target value in an m x n integer matrix. The matrix has the following properties:

* Integers in each row are sorted in ascending from left to right.
* Integers in each column are sorted in ascending from top to bottom.

**Problem type:** Medium

**Link:**   https://leetcode.com/problems/search-a-2d-matrix-ii/
## Code
```java
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        
        int end = matrix[0].length-1;
        int i=0;
        
        if(target<matrix[0][0]) return false;
        
        while(i<matrix.length && end>-1){
            
            if(matrix[i][end]==target) return true;
            
            if(target>matrix[i][end]) i++;
            else  end--;
            
        }
        
        return false;
        
    }
}
```
