# Intersection Point in Y Shapped Linked Lists
---
- ## Question:
> Given two singly linked lists of size N and M, write a program to get the point where two linked lists intersect each other.
---
- ## Example:
> Input:
LinkList1 = 3->6->9->common
LinkList2 = 10->common
common = 15->30->NULL
>
> Output: 15
---
- ## Solution:
**Code :**
```java
class Intersect
{
    //Function to find intersection point in Y shaped Linked Lists.
	int intersectPoint(Node head1, Node head2)
	{
         // code here
         Node temp1=head1;
         Node temp2=head2;
         HashSet<Node>hs=new HashSet<>();
         while(temp1!=null)
         {
             hs.add(temp1);
             temp1=temp1.next;
         }
         while(temp2!=null)
         {
             if(hs.contains(temp2))
             {
                 return temp2.data;
             }
             temp2=temp2.next;
         }
         return -1;
	}
}
