# Insertion Sort
---
- ## Question:
> The task is to complete the insert() function which is used to implement Insertion Sort.
---
- ## Example:
> Input:
N = 5
arr[] = { 4, 1, 3, 9, 7}
>
> Output:
1 3 4 7 9
---
- ## Solution:
**Code :**
```java
class Solution
{
  static void insert(int arr[],int i)
  {
       // Your code here
       for(int j = 0; j < i; j++) {
          
          if(arr[i] < arr[j]) {
              int temp = arr[i];
              arr[i] = arr[j];
              arr[j] = temp;
          }
      }
  }
  //Function to sort the array using insertion sort algorithm.
  public void insertionSort(int arr[], int n)
  {
      //code here
       for(int i = 1; i < n; i++) {
         
         insert(arr, i);
     }
  }
}
