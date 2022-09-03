# Print Anagrams Together
---
- ## Question:
> Given an array of strings, return all groups of strings that are anagrams. The groups must be created in order of their appearance in the original array. Look at the sample case for clarification.
> 
> Note: The final output will be in lexicographic order.
---
- ## Example:
> Input:
N = 5
words[] = {act,god,cat,dog,tac}
>
> Output:
act cat tac 
god dog
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<List<String>> Anagrams(String[] str) {
        // Code here
         HashMap<String,List<String>> map = new HashMap<>();
       
       for (String s:str) {
           
           char arr[] = s.toCharArray();
           Arrays.sort(arr);
           String sort = new String(arr);
           
           if(!map.containsKey(sort)){
               
               map.put(sort,new LinkedList<String>());
           }
           
               map.get(sort).add(s);
           
       }
       
       return new LinkedList<>(map.values());
       
       
   }
}
