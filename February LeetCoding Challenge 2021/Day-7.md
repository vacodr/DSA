# 821. Shortest Distance to a Character
Given a string s and a character c that occurs in s, return an array of integers answer where answer.length == s.length and answer[i] is the shortest distance from s[i] to the character c in s.

Problem type: Easy

link: https://leetcode.com/problems/shortest-distance-to-a-character/
## Code
```java
class Solution {
    public int[] shortestToChar(String s, char c) {
        
        int[] a = new int[s.length()];
        int[] b = new int[s.length()];
        int j=0,k=0;
        
        for(int i=0;i<s.length();i++)
        {
            if(s.charAt(i)==c){
                a[j]=i;
                j++;
            }
        }
        
        for(int i=0;i<s.length();i++)
        {
            if(i>a[k] && a[k+1]>0 && Math.abs(a[k]-i)>a[k+1]-i){
                
                k++;
            }
            
            b[i]=Math.abs(a[k]-i);
        }
        
        return b;
        
    }
}
```
