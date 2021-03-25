[Square root of a number](https://practice.geeksforgeeks.org/problems/square-root/1/?track=amazon-searching&batchId=192)
# Square root of a number 
### 题目大意：
    Given an integer x, find the square root of x. If x is not a perfect square, then return floor(√x).
### 解题思路：
    Use binary search by find the middle value from 0 to x, then check the middle value power of 2 is equal or not to the x, if yes, return middle value;
    if larger than x, high = mid-1, else if smaller than x, low = mid+1
### 注意：
    None
### 复杂度：
    Time: O(LogN)
    Space: O(1)
### Code示例:
```Java
class Solution
{
     long floorSqrt(long x)
	 {
		// Your code here
		if (x <= 1) return x;
		long low = 1, high = x, ans = 0;
		
		while (low <= high) {
		    long mid = low + (high - low) / 2;
		    if (mid * mid == x) return mid;
		    else if (mid * mid < x) low = mid+1;
		    else high = mid-1;
		}
		
		return low - 1;
	 }
}
```
