[Jump Game](https://practice.geeksforgeeks.org/problems/jump-game/1/)
tags: [medium, array] 
# Jump Game
### 题目大意：
    Given an positive integer N and a list of N integers A[]. 
    Each element in the array denotes the maximum length of jump you can cover. 
    Find out if you can make it to the last index if you start at the first index of the list.
### 解题思路：
    First, we initialize variable max as 0, then check each index of element,
    if the current index larger than max, return 0 as false;
    well, if current index  plus current element is larger than current max,
    we will resign max to new value

    when all elements are checked, it means we can reach so return 1 as true.
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(1)
### Code示例:
```Java
class Solution {
    static int canReach(int[] A, int N) {
        // code here
        int max = 0;
        for (int i = 0; i < N; i++) {
            if (i > max) return 0;
            
            max = Math.max(A[i] + i, max);

        }
        
        
        return 1;
    }
}
```
