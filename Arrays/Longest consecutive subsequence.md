[Longest consecutive subsequence](https://practice.geeksforgeeks.org/problems/longest-consecutive-subsequence2449/1)
tags: [array, medium] 
# Longest consecutive subsequence
### 题目大意：
    Given an array of positive integers. Find the length of the longest sub-sequence such that elements in the subsequence are consecutive integers, the consecutive numbers can be in any order.
### 解题思路：
    first we create a hashset to store all unique elements in this array, then we check each element and if set not contiains current element - 1, which means either is not continuous or the smallest element that we find it, .
    Then use j store current element, and use while loop to find how many continious elements that we can find, then just uodate the current ans, if j - arr[i] larger than ans, update it. finally return ans.
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(N)
### Code示例:
```Java
class Solution
{   
    // arr[] : the input array
    // N : size of the array arr[]
    
    //Function to return length of longest subsequence of consecutive integers.
	static int findLongestConseqSubseq(int arr[], int N)
	{
	   // add your code here
	   Set<Integer> set = new HashSet<>();
	   int ans = 0;
	   for (int i = 0; i < N; i++) {
	       set.add(arr[i]);
	   }
	   
	   for (int i = 0; i < N; i++) {
	       if (!set.contains(arr[i] - 1)) {
	           
	           int j = arr[i];
	           
	           while (set.contains(j)) {
	               j++;
	           }
	           
	           if (j - arr[i] > ans) {
	               ans = j - arr[i];
	           }
	       }
	   }
	   
	   return ans;
	}
}
```
