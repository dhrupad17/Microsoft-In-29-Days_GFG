# Add Binary Strings
---
- ## Question:
> Given two binary strings A and B consisting of only 0s and 1s. Find the resultant string after adding the two Binary Strings.
> 
> Note: The input strings may contain leading zeros but the output string should not have any leading zeros.
---
- ## Example:
> Input:
A = "1101", B = "111"
>
> Output: 10100
---
- ## Solution:
**Code :**
```java
class Solution {
    String addBinary(String A, String B) {
        // code heer
        java.math.BigInteger n1=new java.math.BigInteger(A,2);
        java.math.BigInteger n2=new java.math.BigInteger(B,2);
        
        n1=n1.add(n2);
        return n1.toString(2);
    }
}
