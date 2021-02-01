# Level Order Traversal using Recurssion


![Untitled](https://user-images.githubusercontent.com/53373756/106455424-3325be80-64b2-11eb-80bb-6c4d4c78d0f9.png)



```java
class Node
{
    int data;
    Node left;
    Node right;
}

class createNode{

    public Node createNewNode(int value)
    {
        Node a = new Node();
        a.data= value;
        a.left= null;
        a.right = null;

        return a;
    }
}


public class levelorder {


    public static int height(Node root)
    {
        if(root==null){return -1;}
        

        return max(height(root.left),height(root.right))+1;

    }


    private static int max(int a , int b)
    {
        return a>b ? a : b;
    }


    public static void printAtGivenLevel(Node root, int level)
    {
        if(root==null) return;
        if(level==1){
            System.out.printf(root.data+" ");
        }

        printAtGivenLevel(root.left,level-1);
        printAtGivenLevel(root.right,level-1);
    }

    public static void levelOrder(Node root){

        int height = height(root);

        for(int i=0;i<=height;i++){

            printAtGivenLevel(root, i+1);
            System.out.println();
        }
    }


    public static void main(String[] args){

        createNode b = new createNode();
        Node root = b.createNewNode(2);
        root.left = b.createNewNode(7);
        root.right = b.createNewNode(5);
        root.left.left = b.createNewNode(2);
        root.left.right = b.createNewNode(6);
        root.right.right = b.createNewNode(9);
        root.right.right.left = b.createNewNode(4);
        root.left.right.left = b.createNewNode(5);
        root.left.right.right = b.createNewNode(11);

        levelOrder(root);

        
    }
    
}

```
