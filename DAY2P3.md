# Zero Sum Subarrays
---
- ## Question:
> You are given an array arr[] of size n. Find the total count of sub-arrays having their sum equal to 0.
---
- ## Example:
> n = 6
> 
> arr[] = {0,0,5,5,0,0}
> 
> Output: 6
---
- ## Solution:
**Code :**
```java
class Solution{
    //Function to count subarrays with sum equal to 0.
    public static long findSubarray(long[] arr ,int n) 
    {
        //Your code here
        HashMap<Long,Long> map=new HashMap<>();
        long ans=0;
        long sum=0;
        map.put(0l,1l);
        for(int i=0;i<n;i++)
        {
            sum=sum+arr[i];
        if(map.containsKey(sum)){
            ans=ans+map.get(sum);
        }
        if(map.containsKey(sum))
        {
            long k=map.get(sum);
            k++;
            map.put(sum,k);
        }
        else
        {
            map.put(sum,1l);
        }
    }
    return ans;
}
}
