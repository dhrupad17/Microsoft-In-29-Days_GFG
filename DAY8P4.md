# Capacity To Ship Packages Within D Days
---
- ## Question:
> Given an array arr[] of N weights. Find the least weight capacity of a boat to ship all weights within D days.
> 
> The ith weight has a weight of arr[i]. Each day, we load the boat with weights given by arr[i].We may not load more weight than the maximum weight capacity of the ship.
> 
> Note: You have to load weights on the boat in the given order.
---
- ## Example:
> Input:
N = 3
arr[] = {1, 2, 1}
D = 2
> 
> Output:
3
---
- ## Solution:
**Code :**
```java
class Solution {
    static int leastWeightCapacity(int[] arr, int n, int d) {
        // code here
        int low=1;
        int high=0;
        for(int i=0;i<n;i++)
        {
            high=high+arr[i];
        }
        while(low<=high)
        {
            int mid=(low+high)/2;
            if(isPos(arr,n,mid,d))
            {
                high=mid-1;
            }
            else
            {
                low=mid+1;
            }
        }
        return low;
    }
    static boolean isPos(int[] arr, int n,int mid,int d){
        int count=1;
        int sum=0;
        for(int i=0;i<n;i++)
        {
            if(arr[i]>mid)
                return false;
            if(sum+arr[i]<=mid)
            {
                sum=sum+arr[i];
            }
            else
            {
                sum=arr[i];
                count++;
            }
        }
        return count<=d;
    }
};
