# 257. Binary Tree Paths
Given a binary tree, return all root-to-leaf paths.

Note: A leaf is a node with no children.

Problem type: Easy

link: https://leetcode.com/problems/binary-tree-paths/
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
    public List<String> binaryTreePaths(TreeNode root) {
        
        List<String> s = new ArrayList<>();
        String t ="";
        
        leaf(root,s,t);
        
        return s;
        
    }
    
    public void leaf(TreeNode root, List<String> s,String t){
        
        if(root==null) return;
        
        
        if(root.left==null && root.right==null)
        {
            s.add(t+root.val);
        }
        else{
            
            leaf(root.left,s,t+root.val+"->");
        
            leaf(root.right,s,t+root.val+"->");         
        }
        
         
        
        
    }
}
```
