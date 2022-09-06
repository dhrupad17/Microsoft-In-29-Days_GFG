# Reverse a linked list
---
- ## Question:
> Given a linked list of N nodes. The task is to reverse this list.
---
- ## Example:
> Input:
LinkedList: 1->2->3->4->5->6
>
> Output: 6 5 4 3 2 1
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to reverse a linked list.
    Node reverseList(Node head)
    {
        // code here
        Node prev=null;
        while(head!=null)
        {
            Node next=head.next;
            head.next=prev;
            prev=head;
            head=next;
        }
        return prev;
    }
}
