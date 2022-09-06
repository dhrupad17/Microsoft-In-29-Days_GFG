# Reverse a Linked List in groups of given size.
---
- ## Question
> Given a linked list of size N. The task is to reverse every k nodes (where k is an input to the function) in the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should be considered as a group and must be reversed (See Example 2 for clarification).
---
- ## Example:
> Input:
LinkedList: 1->2->2->4->5->6->7->8
K = 4
>
> Output: 4 2 2 1 8 7 6 5 
---
- ## Solution:
**Code :**
```java
class Solution
{
    public static Node reverse(Node node, int k)
    {
        //Your code here
        if(node==null || node.next==null)
            return node;
        Node curr=node;
        Node prev=null;
        Node head=node;
        int i=0;
        while(i<k && curr!=null)
        {
            Node temp=curr.next;
            curr.next=prev;
            prev=curr;
            curr=temp;
            i++;
        }
        if(curr!=null)
        {
            head.next=reverse(curr,k);
        }
        return prev;
    }
}
