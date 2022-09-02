# Permutations of a given string
---
- ## Question:
> Given a string S. The task is to print all unique permutations of the given string in lexicographically sorted order.
---
- ## Example:
> Input: ABC
> 
> Output:
ABC ACB BAC BCA CAB CBA
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<String> find_permutation(String S) {
        // Code here
        char arr[]=S.toCharArray();
        Arrays.sort(arr);
        List<String>ans=new ArrayList<>();
        help(0,arr.length,arr,ans);
        Collections.sort(ans);
        return ans;
    }
    void help(int idx,int n,char[] arr,List<String>ans)
    {
        if(idx==n)
        {
            ans.add(String.valueOf(arr));
            return;
        }
        HashSet<Character>hs=new HashSet<>();
        for(int i=idx;i<n;i++)
        {
            char ch=arr[i];
            if(hs.contains(ch))
                continue;
            else
            {
                hs.add(ch);
            }
            swap(arr,idx,i);
            help(idx+1,n,arr,ans);
            swap(arr,idx,i);
        }
    }
    void swap(char[] arr,int i,int j)
    {
        char temp=arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
    }
}
