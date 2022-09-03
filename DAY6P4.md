# Multiply two strings
---
- ## Question:
> Given two numbers as strings s1 and s2. Calculate their Product.
> 
> Note: The numbers can be negative.
---
- ## Example:
> Input:
s1 = "33"
s2 = "2"
>
> Output:
66
---
- ## Solution:
**Code :**
```java
class Solution
{
    public String multiplyStrings(String s1,String s2)
    {
        //code here.
        java.math.BigInteger a =new java.math.BigInteger(s1);
        java.math.BigInteger b =new java.math.BigInteger(s2);
        b = b.multiply(a);
        return b.toString();
    }
}
