# Left most and right most index
---
- ## Question:
> Given a sorted array with possibly duplicate elements. The task is to find indexes of first and last occurrences of an element X in the given array.
> 
> Note: If the element is not present in the array return {-1,-1} as pair.
---
- ## Example:
> Input:
N = 9
v[] = {1, 3, 5, 5, 5, 5, 67, 123, 125}
X = 5
>
> Output:
2 5
---
- ## Solution:
**Code :**
```java
class Solution {
    
    public pair indexes(long v[], long x)
    {
        // Your code goes here
        long left=bs(v,x,true);
        long right=bs(v,x,false);
        return new pair(left,right);
    }
    public long bs(long[] v,long x,boolean flag)
    {
        int n=v.length;
        int low=0;
        int high=n-1;
        long ans=-1;
        while(low<=high)
        {
            int mid=low+(high-low)/2;
            if(v[mid]==x)
            {
                ans=mid;
                if(flag)
                    high=mid-1;
                else
                    low=mid+1;
            }
            else if(v[mid]<x)
            {
                low=mid+1;
            }
            else
                high=mid-1;
        }
        return ans;
    }
}
