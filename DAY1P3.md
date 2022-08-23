# Key Pair
---
- ## Question:
> Given an array Arr of N positive integers and another number X. Determine whether or not there exist two elements in Arr whose sum is exactly X.
---
- ## Example:
> Input: N = 6, X = 16 Arr[] = {1, 4, 45, 6, 10, 8}
> 
> Output: Yes
> 
> Explanation: Arr[3] + Arr[4] = 6 + 10 = 16
---
- ## Solution:
**Code :**
```java
class Solution {
    boolean hasArrayTwoCandidates(int arr[], int n, int x) {
        // code here
        HashSet<Integer>set=new HashSet<>();
        for(int num: arr)
        {
            if(set.contains(x-num))
            {
                return true;}
                set.add(num);
        }
        return false;
    }
}
