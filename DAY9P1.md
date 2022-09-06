# Check if Linked List is Palindrome
---
- ## Question:
> Given a singly linked list of size N of integers. The task is to check if the given linked list is palindrome or not.
---
- ## Example:
> Input:
N = 3
value[] = {1,2,1}
>
> Output: 1
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to check whether the list is palindrome.
    boolean isPalindrome(Node head) 
    {
        //Your code here
    Node fast = head, slow = head;
    while (fast != null && fast.next != null) {
        fast = fast.next.next;
        slow = slow.next;
    }
    if (fast != null) { // odd nodes: let right half smaller
        slow = slow.next;
    }
    slow = reverse(slow);
    fast = head;
    
    while (slow != null) {
        if (fast.data != slow.data) {
            return false;
        }
        fast = fast.next;
        slow = slow.next;
    }
    return true;
}

public Node reverse(Node head) {
    Node prev = null;
    while (head != null) {
        Node next = head.next;
        head.next = prev;
        prev = head;
        head = next;
    }
    return prev;
}
}
