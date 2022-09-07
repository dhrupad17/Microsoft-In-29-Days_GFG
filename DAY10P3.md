# Add two numbers represented by Linked List
---
- ## Question:
> Given two numbers represented by two linked lists, write a function that returns Sum list. The sum list is linked list representation of addition of two input numbers.
---
- ## Example:
> Input:
S1 = 3, S2 = 3
ValueS1 = {2,3,4}
ValueS2 = {3,4,5}
>
> Output: 5 7 9
---
- ## Solution:
**Code :**
```java
class GfG {

    Node cur; // Dont change the variable name, its used in main function
    int carry; // Dont change the variable name, its used in main function
    
    //This function is called after the smaller list is added to the sublist of 
    //bigger list of same size. Once the right sublist is added, the carry
    //must be added to left side of larger list to get the final result.    
    void addCarryToRemaining(Node head, LinkedList res)  { 
        if(head!=cur)
        {
            addCarryToRemaining(head.next,res);
            int d=head.data+carry;
            res.push(d%10);
            carry=d/10;
        }
        // Write code here
    } 
    
    //Function which adds two linked lists of same size represented by head1  
    //and head2 and returns head of the resultant linked list. Carry
    //is propagated while returning from the recursion    
	void addSameSize(Node head1, Node head2, LinkedList res) { 
	    // Write code here
	    if(head1==null)
	        return;
	    addSameSize(head1.next,head2.next,res);
	    int d=head1.data+head2.data+carry;
	    carry=d/10;
	    res.push(d%10);
    }
} 
