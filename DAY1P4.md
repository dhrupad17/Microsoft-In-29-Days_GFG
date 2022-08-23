# Three Sum Closest
---
- ## Question:
> Given an array, Arr of N numbers, and another number target, find three integers in the array such that the sum is closest to the target. Return the sum of the three integers.
> 
> Note: If there are multiple solutions, print the maximum one.
---
- ## Example:
> Input: N = 6, target = 2 A[] = {-7,9,8,3,1,1}
> 
> Output: 2
> 
> Explanation: There is one triplet with sum 2 in the array. Triplet elements are -7,8, 1 whose sum is 2.
---
- ## Solution:
**Code :**
```java
class Solution 
{ 
   
static int ans = Integer.MIN_VALUE;
static int diff = Integer.MAX_VALUE;

   static int threeSumClosest(int[] array, int target)  
{ 
    ans = 0;
    diff = Integer.MAX_VALUE;
       dfs(0, 0, 0, array, target);
       return ans;
}


static void dfs(int idx, int cnt, int sum, int [] arr, int target){
    if(diff == 0) return;
    
    if(cnt == 3){
        if(sum == target){
            ans = sum;
            diff = 0;
            return;
        }
        
        int d = Math.abs(target-sum);
        if(diff == d){
            ans = Math.max(ans, sum);
            return;
        }
        
        if(d < diff){
            diff = d;
            ans = sum;
            return;
        }
        return;
    }
    
    
    if(idx == arr.length) return;
    
    dfs(idx + 1, cnt + 1, sum + arr[idx], arr, target);
    dfs(idx + 1, cnt, sum, arr, target);
}
}  
