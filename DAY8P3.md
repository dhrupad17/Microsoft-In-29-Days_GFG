# First and last occurrences of X
---
- ## Question:
> Given a sorted array having N elements, find the indices of the first and last occurrences of an element X in the given array.
> 
> Note: If the number X is not found in the array, return '-1' as an array.
---
- ## Example:
> Input:
N = 4 , X = 3
arr[] = { 1, 3, 3, 4 }
>
> Output:
1 2
---
- ## Solution:
**Code :**
```java
class Solution{
    public ArrayList<Integer> firstAndLast(int arr[], int n, int x){
        // Code here
        ArrayList<Integer>list=new ArrayList<>();
        ArrayList<Integer>list1=new ArrayList<>();
        for(int i=0;i<n;i++)
        {
            list.add(arr[i]);
        }
        int a=list.indexOf(x);
        int b=list.lastIndexOf(x);
        if(a==-1 && b==-1)
            list1.add(-1);
        else
        {
            list1.add(a);
            list1.add(b);
        }
        return list1;
        
    }
}
