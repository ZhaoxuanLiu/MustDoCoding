[Frequencies of Limited Range Array Elements](https://practice.geeksforgeeks.org/problems/frequency-of-array-elements-1587115620/1)
tags: [easy, array] 
# Frequencies of Limited Range Array Elements
### 题目大意：
    Given an array A[] of n positive integers which can contain integers from 1 to P where elements can be repeated or can be absent from the array. Your task is to count the frequency of all elements from 1 to n.
### 解题思路：
    since we need to find the frequency of from 1 to n, first we make the elemnts from 1 to n chenge to 0 to n-1;
    Considering the boudry of exception, we need to mod to the size of n
    
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(1)
### Code示例:
```Java
class Solution{
    //Function to count the frequency of all elements from 1 to N in the array.
    public static void frequencycount(int arr[], int n)
    {
        // code here
        int[] count = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = arr[i] - 1;
        }
        
        
        for (int i = 0; i < n; i++) {
            arr[arr[i]%n] = arr[arr[i]%n] + n;
        }
        
        for (int i = 0; i < n; i++) {
            arr[i] = arr[i] / n;
        }
    }
}
```
