[Maximum Index](https://practice.geeksforgeeks.org/problems/maximum-index-1587115620/1)
tags: [array, medium] 
# Maximum Index
### 题目大意：
    Given an array A[] of N positive integers. The task is to find the maximum of j - i subjected to the constraint of A[i] <= A[j].
### 解题思路：
    first, we create new int array with the same length of n representing as left and right, use left to store the minimum value between current element and past element; use right to store the maximum value between the current element and next element.

    Initialize three index i, j, and ans to represent as index
    as long as i and j  smaller than length n, and the element pointed to index i smaller than the element pointed to index j.
    update ans to take larger value between j - i and current ans.

    finally return ans
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(N)
### Code示例:
```Java
class Solution{
    
    // arr[]: input array
    // n: size of array
    // Function to find the maximum index difference.
    static int maxIndexDiff(int arr[], int n) { 
        
        // Your code here
        if (n == 1) return 0;
        
        int[] left = new int[n];
        int[] right = new int[n];
        
        left[0] = arr[0];
        for (int i = 1; i < n; i++) {
            left[i] = Math.min(arr[i], left[i-1]);
        }
        
        right[n-1] = arr[n-1];
        for (int i = n-2; i >= 0; i--) {
            right[i] = Math.max(arr[i], right[i+1]);
        }
        
        int i = 0, j = 0, ans = -1;
        
        while (i < n && j < n) {
            if (left[i] <= right[j]) {
                ans = Math.max(j-i, ans);
                j++;
            } else {
                i++;
            }
        }
        
        return ans;
    }
}
```
