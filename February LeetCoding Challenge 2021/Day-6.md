# 199. Binary Tree Right Side View
Given a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.

Problem type: Medium

link: https://leetcode.com/problems/binary-tree-right-side-view/
# Code
```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<Integer> rightSideView(TreeNode root) {
        
        List<Integer> l = new ArrayList<>();
        
        right(root,0,l);
        
        return l;     
        
    }
    
    int max=0;
    
    public void right(TreeNode root, int level,List<Integer>l){
        
        if(root==null) return;
        
        if(level>=max)
        {
            l.add(root.val);
            max++;
        }
           
        right(root.right,level+1,l);
        right(root.left,level+1,l);
        
    }
}
```
