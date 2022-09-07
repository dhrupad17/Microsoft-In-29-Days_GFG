# Length of longest palindrome in linked list
---
- ## Question:
> Given a linked list, the task is to complete the function maxPalindrome() which returns an integer denoting  the length of the longest palindrome list that exist in the given linked list.
---
- ## Example:
> Input:
2
7
2 3 7 3 2 12 24
5
12 4 4 3 14
>
> Output:
5
2
---
- ## Solution:
**Code :**
```java
class GfG
{
        public static int maxPalindrome(Node head)
        {
          //add code here.
           int len = 1;
          Node prv = null;
          Node next = null;
          while(head!=null) {
               //reverse
              next = head.next;
              head.next = prv;
              
              
              len = Math.max(len,2*count(prv,next)+1);
              len = Math.max(len,2*count(head,next));
              
              prv = head;
              head = next;
             
          }
          return len;
        }
       static int count(Node cur1,Node cur2) {
            int count = 0;
            while(cur1!=null&&cur2!=null&&cur1.data==cur2.data) {
                count++;
                cur1 = cur1.next;
                cur2 = cur2.next;
            }
            return count;
        }
}
