# Longest subarray with sum divisible by K
---
- ## Question:
> Given an array containing N integers and a positive integer K, find the length of the longest sub array with sum of the elements divisible by the given value K.
---
- ## Example:
> Input: A[] = {2, 7, 6, 1, 4, 5}
>
> K = 3
>
> Output: 4
>
> Explanation:The subarray is {7, 6, 1, 4}
>
> with sum 18, which is divisible by 3.
---
- ## Solution:
**Code :**
```java
class Solution{
    int longSubarrWthSumDivByK(int a[], int n, int k)
    {
        // Complete the function
        int ans=0;
        int sum=0;
        int rem=0;
        HashMap<Integer,Integer> map=new HashMap<>();
        map.put(0,-1);
        for(int i=0;i<n;i++)
        {
            sum=sum+a[i];
            rem=sum%k;
            if(rem<0){
                rem=rem+k;
            }
            if(map.containsKey(rem)){
                int idx=map.get(rem);
                int len=i-idx;
                if(len>ans){
                    ans=len;
                }
            }
            else{
                map.put(rem,i);
            }
        }
        return ans;
       
    }
 
}
