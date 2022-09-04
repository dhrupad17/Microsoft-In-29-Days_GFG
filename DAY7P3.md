# Coin Piles
---
- ## Question:
> There are N piles of coins each containing  Ai (1<=i<=N) coins. Find the minimum number of coins to be removed such that the absolute difference of coins in any two piles is at most K.
> 
> Note: You can also remove a pile by removing all the coins of that pile.
---
- ## Example:
> Input:
N = 4, K = 0
arr[] = {2, 2, 2, 2}
>
> Output:
0
---
- ## Solution:
**Code :**
```java
class Solution {
    static int minSteps(int[] arr, int n, int k) {

        Arrays.sort(arr);
        
        int[] subset = new int[n];
        subset[n-1] = arr[n-1];
        for(int i =n-2 ; i >= 0 ; i--){
            subset[i] = arr[i] + subset[i+1];
        }
        
        int min = Integer.MAX_VALUE;
        int sum = 0;
        
        for(int i =0; i< n; i++){
            int ind = findUpper(arr , arr[i] + k , i , n-1);
            if(ind == -1){
                min = Math.min(min , sum); 
                continue;
            }
            
            int curr = subset[ind] - ((n - ind) *(arr[i]+k));
            curr += sum;
            
            min = Math.min(min , curr);
            sum += arr[i];
        }
        
        return min;
        
    }
    
    static int findUpper(int[] arr , int target,  int s , int e){
        
        int ans = -1;
        
        while(s <= e){
            
            int mid = (s+e)/2;
            
            if(arr[mid] > target){
                ans = mid;
                e = mid - 1;
            }
            else{
                s = mid + 1;
            }   
        }
        return ans;
        
    } 
  
};
