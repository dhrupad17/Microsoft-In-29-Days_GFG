# The Painter's Partition Problem-II
---
- ## Question:
> Dilpreet wants to paint his dog's home that has n boards with different lengths. The length of ith board is given by arr[i] where arr[] is an array of n integers. He hired k painters for this work and each painter takes 1 unit time to paint 1 unit of the board. 
> 
> The problem is to find the minimum time to get this job done if all painters start together with the constraint that any painter will only paint continuous boards, say boards numbered {2,3,4} or only board {1} or nothing but not boards {2,4,5}.
---
- ## Example:
> Input:
n = 5
k = 3
arr[] = {5,10,30,20,15}
>
> Output: 35
---
- ## Solution:
**Code :**
```java
class Solution{
    static long minTime(int[] arr,int n,int k){
        //code here
        long low=0;
        long high=0;
        for(int i=0;i<n;i++)
        {
            low=Math.max(low,arr[i]);
            high=high+arr[i];
        }
        long ans=0;
        while(low<=high)
        {
            long sum=0;
            long mid=low+(high-low)/2;
            int painter=1;
            for(int i=0;i<n;i++)
            {
                sum=sum+arr[i];
                if(sum>mid)
                {
                    sum=arr[i];
                    painter++;
                }
            }
           if(painter<=k)
           {
               ans=mid;
               high=mid-1;
           }
           else
           {
               low=mid+1;
           }
           
        }
        return ans;
    }
}


