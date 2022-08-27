# Non Repeating Character
---
- ## Question:
> Given a string S consisting of lowercase Latin Letters. Return the first non-repeating character in S. If there is no non-repeating character, return '$'.
---
- ## Example:
> S = hello
> 
> Output: h
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to find the first non-repeating character in a string.
    static char nonrepeatingCharacter(String s)
    {
        //Your code here
        for(int i=0;i<s.length();i++)
        {
            if(s.indexOf(s.charAt(i))==s.lastIndexOf(s.charAt(i)))
            {
                return s.charAt(i);
            }
        }
        return '$';
    }
}
