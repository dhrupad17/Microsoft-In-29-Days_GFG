# Finding middle element in a linked list
---
- ## Question:
> Given a singly linked list of N nodes.
> 
> The task is to find the middle of the linked list. For example, if the linked list is
> 
> 1-> 2->3->4->5, then the middle node of the list is 3.
> 
> If there are two middle nodes(in case, when N is even), print the second middle element.
> 
> For example, if the linked list given is 1->2->3->4->5->6, then the middle node of the list is 4.
---
- ## Example:
> Input:
LinkedList: 1->2->3->4->5
>
> Output: 3 
---
- ## Solution:
**Code :**
```java
class Solution
{
    int getMiddle(Node head)
    {
         // Your code here.
        Node p1,p2;
        p1=head;
        p2=head;
        while(p2!=null && p2.next!=null)
        {
            p1=p1.next;
            p2=p2.next.next;
        }
        return p1.data;
    }
}
