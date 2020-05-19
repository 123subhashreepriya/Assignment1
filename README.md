# Assignment1

import java.util.LinkedList;
import java.util.Queue;

public class Assignment1
{

public static void main(String[] args) {

Node root = new Node(1);
root.right= new Node(2);
root.right.right = new Node(5);
root.right.right.left = new Node(3);
root.right.right.right = new Node(6);
root.right.right.left.right = new Node(4);

BFSTraversal(root);

}

private static void BFSTraversal(Node root) {
Queue<Node> queue= new LinkedList<Node>();

if(root == null){
return;
}

queue.add(root);

while(!queue.isEmpty()){
Node n = queue.remove();
System.out.print(n.data);
if(n.left != null || n.right != null || !queue.isEmpty()){
System.out.print(" -> ");
}

if(n.left != null){
queue.add(n.left);
}
if(n.right != null){
queue.add(n.right);
}
}

}

static class Node
{
int data;
Node left;
Node right;

public Node(int data)
{
this.data=data;
left=null;
right=null;
}
}
}
