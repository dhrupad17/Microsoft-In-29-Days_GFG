# Find missing in second array
---
- ## Question:
> Given two arrays A and B contains integers of size N and M, the task is to find numbers which are present in the first array, but not present in the second array.
---
- ## Example:
> Input: N = 6, M = 5
> 
> A[] = {1, 2, 3, 4, 5, 10}
> 
> B[] = {2, 3, 1, 0, 5}
> 
> Output: 4 10
---
- ## Solution:
**Code :**
```java
class Solution
{
    ArrayList<Long> findMissing(long A[], long B[], int N, int M)
    {
        ArrayList<Long> ans=new ArrayList<>();
        HashSet<Long> set=new HashSet<>();
        for(int i=0;i<M;i++)
        {
            set.add(B[i]);
        }
        for(int i=0;i<N;i++)
        {
            if(!set.contains(A[i]))
                ans.add(A[i]);
        }
        return ans;
    }
}
