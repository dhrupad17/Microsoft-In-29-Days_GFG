# Triplet Sum in Array
---
- ## Question:
> Given an array arr of size n and an integer X. Find if there's a triplet in the array which sums up to the given integer X.
---
- ## Example:
> Input:
n = 6, X = 13
arr[] = [1 4 45 6 10 8]
>
> Output:
1
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to find if there exists a triplet in the 
    //array A[] which sums up to X.
    public static boolean find3Numbers(int A[], int n, int X) { 
    
       // Your code Here
       Arrays.sort(A);
       for(int i=0;i<n;i++)
       {
           int y=X-A[i];
           int low=i+1;
           int high=n-1;
           while(low<high)
           {
               if(A[low]+A[high]==y)
                return true;
                else if(A[low]+A[high]>y)
                    high--;
                else
                    low++;
           }
       }
       return false;
    }
}
