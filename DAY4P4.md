# Top K Frequent Elements in Array
---
- ## Question:
> Given a non-empty array of integers, find the top k elements which have the highest frequency in the array. If two numbers have the same frequency then the larger number should be given preference. 
> 
> Note: Print the elements according to the frequency count (from highest to lowest) and if the frequency is equal then larger number will be given preference.
---
- ## Example:
> Input:
N = 6
nums = {1,1,1,2,2,3}
k = 2
>
> Output: {1, 2}
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[] topK(int[] nums, int k) {
        Map<Integer,Integer> map=new HashMap<>();
        for(int x:nums){
            map.put(x,map.getOrDefault(x,0)+1);
        }
        Integer[] arr=new Integer[map.size()];
        int start=0;
        for(Integer key:map.keySet()){
            arr[start++]=key;
        }
        Arrays.sort(arr,new cmp(map));
        int[] result=new int[k];
        for(int i=0;i<k;i++){
            result[i]=arr[i];
        }
        return result;
    }
}
