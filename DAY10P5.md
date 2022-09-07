# Merge K sorted linked lists
---
- ## Question:
> Given K sorted linked lists of different sizes. The task is to merge them in such a way that after merging they will be a single sorted linked list.
---
- ## Example:
> Input:
K = 4
value = {{1,2,3},{4 5},{5 6},{7,8}}
>
> Output: 1 2 3 4 5 5 6 7 8
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to merge K sorted linked list.
    Node mergeKList(Node[]arr,int K)
    {
        //Add your code here.
        if(arr.length==0)
            return null;
        return mergeList(arr,0,arr.length-1);
    }
    Node mergeList(Node[] arr, int a,int b)
    {
        if(a>b)
        {
            return null;
        }
        if(a==b)
            return arr[a];
        int mid=a+(b-a)/2;
        Node n1=mergeList(arr,a,mid);
        Node n2=mergeList(arr,mid+1,b);
        return mergeTwoList(n1,n2);
    }
    Node mergeTwoList(Node list1, Node list2){
       Node head = new Node(-1);
       Node p = head;
       Node p1 = list1;
       Node p2 = list2;
        
       while(p1 != null && p2 != null){
           if(p1.data < p2.data){
               p.next = p1;
               p1 = p1.next;
           }
          else {
               p.next = p2;
               p2 = p2.next;
           }
           p = p.next;
       }
        if(p1 != null){p.next = p1;}
        if(p2 != null){p.next = p2;}
        
        return head.next;
    }
    
}
