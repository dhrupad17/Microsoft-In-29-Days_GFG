# Merge Sort
---
- ## Question:
> Given an array arr[], its starting position l and its ending position r. Sort the array using merge sort algorithm.
---
- ## Example:
> Input:
N = 5
arr[] = {4 1 3 9 7}
>
> Output:
1 3 4 7 9
---
- ## Solution:
**Code :**
```CPP
class Solution
{
    public:
    void merge(int arr[], int low, int mid, int high)
{
	int i=low, j=(mid+1), k=low;
	int aux[high+1];
	while(i<=mid && j<=high)
	{
		if(arr[i]<=arr[j])
		{
			aux[k]=arr[i];
			i++;
		}
		else
		{
			aux[k]=arr[j];
			j++;
		}
		k++;
	}
	while(i<=mid)
	{
		aux[k]=arr[i];
		i++;
		k++;
	}
	while(j<=high)
	{
		aux[k]=arr[j];
		j++;
		k++;
	}
	for(i=low;i<=high;i++)
		arr[i]=aux[i];
}
    public:
    void mergeSort(int arr[], int low, int high)
{
	if(low<high)
	{
		int mid=low+(high-low)/2;
		mergeSort(arr,low,mid);
		mergeSort(arr,mid+1,high);
		merge(arr,low,mid,high);
	}
}
};

// { Driver Code Starts.


int main()
{
    int n,T,i;

    scanf("%d",&T);

    while(T--){
    
    scanf("%d",&n);
    int arr[n+1];
    for(i=0;i<n;i++)
      scanf("%d",&arr[i]);

    Solution ob;
    ob.mergeSort(arr, 0, n-1);
    printArray(arr, n);
    }
    return 0;
}  // } Driver Code Ends
