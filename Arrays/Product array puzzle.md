[Product array puzzle](https://practice.geeksforgeeks.org/problems/product-array-puzzle4525/1)
tags: [easy, array] 
# Product array puzzle
### 题目大意：
    Given an array A[] of size N, construct a Product Array P (of same size N) 
    such that P[i] is equal to the product of all the elements of A except A[i].

### 解题思路：

### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(N)
### Code示例:
```Java
class Solution 
{ 
	public static long[] productExceptSelf(int arr[], int n) 
	{ 
        // code here
        long[] ans = new long[n];
        if (n == 1) {
            ans[0] = 1;
            return ans;
        }
        
        long tmp = 1;
        for (int i = 0; i < n; i++) {
            ans[i] = 1;
            ans[i] = tmp;
            tmp *= arr[i];
        }
        
        
        tmp = 1;
        for (int i = n-1; i >= 0; i--) {
            ans[i] *= tmp;
            tmp *= arr[i];
        }
        
        return ans;
	} 
} 
```
