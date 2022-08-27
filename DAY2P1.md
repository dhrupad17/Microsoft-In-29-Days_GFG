# Count distinct elements in every window
---
- ## Question:
> Given an array of integers and a number K. Find the count of distinct elements in every window of size K in the array.
---
- ## Example:
> N = 7, K = 4
> 
> A[] = {1,2,1,3,4,2,3}
> 
> Output: 3 4 4 3
---
- ## Solution:
**Code :**
```java
class Solution
{
    ArrayList<Integer> countDistinct(int A[], int n, int k){
        
        ArrayList<Integer> list = new ArrayList<>();
        Map<Integer,Integer> map = new HashMap<>();
        for(int i=0;i<k;i++){
            if(map.containsKey(A[i]))
                map.put(A[i],map.get(A[i])+1 );
            else
                map.put(A[i],1);
        }
        list.add(map.size());
        for(int i=1;i<n-k+1;i++){
            
            // remove i-1;
            map.put(A[i-1], map.get(A[i-1])-1);
            if(map.get(A[i-1])==0)
                map.remove(A[i-1]);
            map.put( A[i+k-1], map.getOrDefault(A[i+k-1],0)+1 );
            list.add(map.size());
            
        }
        return list;
        
    }
}
