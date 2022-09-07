# Remove all occurences of duplicates in a linked list
---
- ## Question:
> Given a sorted linked list, delete all nodes that have duplicate numbers (all occurrences), leaving only numbers that appear once in the original list. 
---
- ## Example:
> Input: 
N = 8
Linked List = 23->28->28->35->49->49->53->53
>
> Output: 
23 35
---
- ## Solution:
**Code :**
```java
class Solution
{
    public static Node removeAllDuplicates(Node head)
    {
        //code here
        Node dummy=new Node(0);
        dummy.next=head;
        Node prev=dummy;
        Node curr=head;
        while(curr!=null)
        {
            while(curr.next!=null && curr.next.data==prev.next.data)
            {
                curr=curr.next;
            }
            if(prev.next==curr)
            {
                prev=prev.next;
            }
            else
            {
                prev.next=curr.next;
                curr=curr.next;
            }
        }
        head=dummy.next;
        return head;
        
    }
}
