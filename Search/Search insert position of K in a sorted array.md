[Search insert position of K in a sorted array](https://practice.geeksforgeeks.org/problems/search-insert-position-of-k-in-a-sorted-array/1/#)
tags: [search, easy] 
# Search insert position of K in a sorted array
### 题目大意：
    Given a sorted array Arr[](0-index based) consisting of N distinct integers and an integer k, the task is to find the index of k, if it’s present in the array Arr[]. Otherwise, find the index where k must be inserted to keep the array sorted.
### 解题思路：
    binary search first, then compare the element pointed by low index with k
    if arr[low] >= k, return low;
    else return low+1;
### 注意：
    None
### 复杂度：
    Time:O(logN)
    Space: O(1)
### Code示例:
```Java
class Solution
{
    static int searchInsertK(int Arr[], int N, int k)
    {
        // code here
        int low = 0, high = N-1;
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (Arr[mid] == k) return mid;
            else if (Arr[mid] < k) low = mid+1;
            else high = mid - 1;
        }
        
        if (Arr[low] < k) {
            return low+1;
        } else if (Arr[low] == k) {
            return low;
        } else {
            return low;
        }
    }
}
```
