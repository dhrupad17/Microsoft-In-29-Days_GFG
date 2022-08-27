# Array Pair Sum Divisibility Problem
---
- ## Question:
> Given an array of integers and a number k, write a function that returns true if given array can be divided into pairs such that sum of every pair is divisible by k.
---
- ## Example:
> Input : arr = [9, 5, 7, 3], k = 6
> 
> Output: True
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean canPair(int[] arr, int k) {
        // Code here
        HashMap<Integer,Integer> map = new HashMap<>();
        
        for(int i = 0 ; i < arr.length; i++){
            
            int currRem = ((arr[i]%k)+k)%k;
            
            if(map.containsKey(currRem)){
                map.put(currRem, map.get(currRem)+1);
            }
            
            else{
                map.put(currRem,1);
            }
        }
        
        
        for(int key : map.keySet()) {
    		
    		
    		if(key == 0) {
    			
    			if(map.get(key)%2!=0)
    				return false;
    		}
    		
    		else if(!map.get(key).equals(map.get(k-key)))
    			return false;
    	}
        
        return true;
        
    }
}
