[Search an element in sorted and rotated array](https://practice.geeksforgeeks.org/problems/search-in-a-rotated-array0959/1/?track=amazon-searching&batchId=192)
# Search an element in sorted and rotated array
### 题目大意：
    Given a sorted and rotated array A of N distinct elements which is rotated at some point, and given an element K. The task is to find the index of the given element K in the array A.
### 解题思路：
    use binary searchi to find the mid index element and compare it with target, if equal, we find it and return mid index, 
    if current mid index element larger or equal to the low index element, we need to move close to check whether the mid idnex value  larger than target and target larger than or equal to low index element, high = mid -1; otherwise low = mid+1;

    if current mid index value smaller than high index value, we need to check one more step: whether mid index value smaller than target and target smaller than or equal to high index value, if so, low = mid + 1;
    otherwise high = mid - 1

    if low > high, return -1
### 注意：
    None
### 复杂度：
    Time:
    Space: 
### Code示例:
```Java
class Solution 
{ 
    static int Search(int array[], int target)
	{
	    // code here
	    
	    int low = 0, high = array.length-1;
	    while  (low <= high) {
	        int mid = low + (high - low) / 2;
	        if (array[mid] == target) return mid;
	        
	        if (array[mid] >= array[low]) {
	            if (array[mid] > target && target >= array[low]) high = mid-1;
	            else low = mid + 1;
	        }
	        
	        if (array[mid] < array[high]) {
	            if (array[mid] < target && target <= array[high]) low = mid+1;
	            else high = mid - 1;
	        }
	    }
	    
	    return -1;
	}
} 

```
