[K-th element of two sorted Arrays](https://practice.geeksforgeeks.org/problems/k-th-element-of-two-sorted-array1317/1)
tags: [array, medium] 
# K-th element of two sorted Arrays
### 题目大意：
    Given two sorted arrays arr1 and arr2 of size M and N respectively and an element K. The task is to find the element that would be at the k’th position of the final sorted array.
### 解题思路：
    since two arraies are sorted, first we can merge these two sorted array.
    then kth is 1 index based, we just need to return k-1 element
### 注意：
    None
### 复杂度：
    Time:O(N + M)
    Space: O(N + M)
### Code示例:
```Java
class Solution {
    public long kthElement( int arr1[], int arr2[], int n, int m, int k) {
        int[] ans = new int[n+m];
        
        int i = 0, j = 0, l = 0;
        while (i < n && j < m) {
            if (arr1[i] <= arr2[j]) {
                ans[l] = arr1[i];
                i++;
            } else {
                ans[l] = arr2[j];
                j++;
            }
            
            l++;
        }
        
        if(i == n) {
            while (j < m) {
                ans[l++] = arr2[j++];
            }
        }
        
        if (j == m) {
            while (i < n) {
                ans[l++] = arr1[i++];
            }
        }
        
        return ans[k-1];
        
    }
}
```
