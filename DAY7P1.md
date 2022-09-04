# Distribute N candies among K people
---
- ## Question:
> Given N candies and K people. In the first turn, the first person gets 1 candy, the second gets 2 candies, and so on till K people. In the next turn, the first person gets K+1 candies, the second person gets K+2 candies and so on. If the number of candies is less than the required number of candies at every turn, then the person receives the remaining number of candies. Find the total number of candies every person has at the end.
---
- ## Example:
> Input:
N = 7, K = 4
>
> Output:
1 2 3 1
---
- ## Solution:
**Code :**
```java
class Solution {
    static Long[] distributeCandies(int n, int k) {
        // code here
        Long ans[]=new Long[k];
        Arrays.fill(ans,0l);
        int start=0;
        while(n>0)
        {
            if(n>start){
            ans[start%k]=ans[start%k]+(start+1);
            n=n-start-1;
            start++;
            }
            else{
                ans[start%k]=ans[start%k]+n;
                break;
            }
        }
        return ans;
    }
};
