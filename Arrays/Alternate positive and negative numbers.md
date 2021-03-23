[Alternate positive and negative numbers](https://practice.geeksforgeeks.org/problems/array-of-alternate-ve-and-ve-nos1401/1)
tags: [easy, array] 
# Alternate positive and negative numbers
### 题目大意：
    Given an unsorted array Arr of N positive and negative numbers. 
    Your task is to create an array of alternate positive and negative numbers 
    without changing the relative order of positive and negative numbers.
    Note: Array should start with positive number.
### 解题思路：
    first we create two arraylist to store psotive number and negative number
    then add postive number and negative number aternativly
    since tow list size might not be equal, we put rest of elements which the the index 
    is still smaller than its size into list
### 注意：
    None
### 复杂度：
    Time:O(N)
    Space: O(N)
### Code示例:
```Java

class Solution {
    void rearrange(int arr[], int n) {
        if (arr == null || arr.length <= 1) return;
        // code here
        List<Integer> positive = new ArrayList<Integer>();
        List<Integer> negative = new ArrayList<Integer>();
        
        for (int num : arr) {
            if (num < 0) negative.add(num);
            else positive.add(num);
        }
        
        int i = 0, j = 0, k = 0;
        while (i < positive.size() && j < negative.size()) {
            arr[k++] = positive.get(i++);
            arr[k++] = negative.get(j++);
        }
        
        while (i < positive.size()) arr[k++] = positive.get(i++);
        
        while (j < negative.size()) arr[k++] = negative.get(j++);
    }
}
```
