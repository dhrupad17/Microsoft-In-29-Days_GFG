# Killing Spree
---
- ## Question:
> There are Infinite People Standing in a row, indexed from 1.
> 
> A person having index 'i' has strength of (i*i).
> 
> You have Strength 'P'. You need to tell what is the maximum number of People You can Kill With your Strength P.
> 
> You can only Kill a person with strength 'X' if P >= 'X'  and after killing him, Your Strength decreases by 'X'. 
---
- ## Example:
> Input:
N = 14
>
> Output: 3
---
- ## Solution:
**Code :**
```java
class Solution{
    
    long killinSpree(long n)
    {
        // Code Here
        long l=1;
        long r=100000;
        while(l<r)
        {
            long mid=(l+r+1)/2;
            if(n>=(mid)*(mid+1)*(2*mid+1)/6)
                l=mid;
            else
                r=mid-1;
        }
        return l;
    }
}
