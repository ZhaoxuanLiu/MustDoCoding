[Maximize Number of 1's ](https://practice.geeksforgeeks.org/problems/maximize-number-of-1s0905/1)
tags: [medium, array] 
# Maximize Number of 1's 
### 题目大意：
    Given a binary array arr of size N and an integer M. Find the maximum number of consecutive 1's produced by flipping at most M 0's.
### 解题思路：
    first initialize some variables such as L and R representing as pointer left and pointer right, ans represnting as final answer, zeros as the number of zero.

    then we use R pointer to point element from left to right as long as R is smaller than the size of array.

    if the number of zeros smaller than given m, and if pointer R point to the element of array equal to 0, zeros++, R++

    if the number of zeros larger than given m, and if pointer L point to the element of array equal to 0, zeros--, L++

    if the difference between R and L larger the current ans and the number of zeros smaller or equal than m, 
    assign ans equal to the difference between R and L


    finally return ans
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(1)
### Code示例:
```Java
class Solve {
    // m is maximum of number zeroes allowed to flip
    int findZeroes(int arr[], int n, int m) {
        // code here
        int R = 0, L = 0;
        int ans = 0;
        int zeros = 0;
        
        while (R < n) {
            if (zeros <= m) {
                if (arr[R] == 0) zeros++;
                
                R++;
            }
            
            if (zeros > m) {
                if (arr[L] == 0) zeros--;
                
                L++;
            }
            
            if ((R - L) > ans && zeros <= m) {
                ans = R - L;
            }
            
        }
        
        return ans;
    }
}
```
