# 113. Path Sum II
Given the root of a binary tree and an integer targetSum, return all root-to-leaf paths where each path's sum equals targetSum.

A leaf is a node with no children.

Problem type: Medium

link: https://leetcode.com/problems/path-sum-ii/
## Code
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
    
    ArrayList<Integer> l;
    public List<List<Integer>> pathSum(TreeNode root, int targetSum) {
        
        List<List<Integer>> l2 = new ArrayList<>();
        
        List<Integer> l1 = new ArrayList<>();
        
        sum(root,targetSum,l1,l2);
        
        return l2;
        
    }
    
    public void sum(TreeNode root, int targetSum,List<Integer>l1,List<List<Integer>>l2){
        
        if(root==null) return ;
        
        l1.add(root.val);
        
        if(root.left==null && root.right==null && root.val==targetSum)
        {
            l2.add(new ArrayList(l1));
        }
        else{
            
             sum(root.left,targetSum-root.val,l1,l2);

             sum(root.right,targetSum-root.val,l1,l2);
            
        }
        
        l1.remove(l1.size()-1);
        
        
    }
}
```
