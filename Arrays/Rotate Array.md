[Rotate Array](https://practice.geeksforgeeks.org/problems/rotate-array-by-n-elements-1587115621/1)
tags: [array, easy] 
# Rotate Array
### 题目大意：
    Given an unsorted array arr[] of size N, rotate it by D elements in the counter-clockwise direction. 

    Example 1:
        Input:
        N = 5, D = 2
        arr[] = {1,2,3,4,5}
        Output: 3 4 5 1 2
        Explanation: 1 2 3 4 5  when rotated
        by 2 elements, it becomes 3 4 5 1 2.
    Example 2:
        Input:
        N = 10, D = 3
        arr[] = {2,4,6,8,10,12,14,16,18,20}
        Output: 8 10 12 14 16 18 20 2 4 6
        Explanation: 2 4 6 8 10 12 14 16 18 20 
        when rotated by 3 elements, it becomes 
        8 10 12 14 16 18 20 2 4 6.
### 解题思路：
    first rotate all elements of this array first,
    then rotate elements with index from 0 to n-d-1
    finally rotate elements wih index from n-d to n-1
    n is the length of array
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(1)
### Code示例:
```Java
class Solution
{
    //Function to rotate an array by d elements in counter-clockwise direction. 
    static void rotateArr(int arr[], int d, int n)
    {
        // add your code here
        
        int i = 0, j = n-1, tmp = 0;
        while (i < j) {
            tmp = arr[i];
            arr[i] = arr[j];
            arr[j] = tmp;
            i++;
            j--;
        }
        
        i = 0;
        j = n-d-1;
        while (i < j) {
            tmp = arr[i];
            arr[i] = arr[j];
            arr[j] = tmp;
            i++;
            j--;
        }
        
        i = n - d;
        j = n-1;
        while (i < j) {
            tmp = arr[i];
            arr[i] = arr[j];
            arr[j] = tmp;
            i++;
            j--;
        }
    }
}
```
