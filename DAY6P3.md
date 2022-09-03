# Longest Prefix Suffix
---
- ## Question:
> Given a string of characters, find the length of the longest proper prefix which is also a proper suffix.
> 
> NOTE: Prefix and suffix can be overlapping but they should not be equal to the entire string.
---
- ## Example:
> Input: s = "abab"
> 
> Output: 2
---
- ## Solution:
**Code :**
```java
class Solution {
   int lps(String s) {
       // code here
       int[] lps = new int[s.length()];

       int i=1,len=0;

       while(i<s.length()){

           if(s.charAt(i)==s.charAt(len)){
               len++;
               lps[i]=len;
               i++;
           }else{
               if(len>0){
                   len = lps[len-1];
               }else{
                   lps[i]=0;
                   i++;
               }
           }
       }
       return lps[s.length()-1];
   }
}
