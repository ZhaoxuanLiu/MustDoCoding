[Left most and right most index](https://practice.geeksforgeeks.org/problems/find-first-and-last-occurrence-of-x0849/1#)
# Left most and right most index 
### 题目大意：
    Given a sorted array with possibly duplicate elements. The task is to find indexes of first and last occurrences of an element X in the given array.

    Note: If the element is not present in the array return {-1,-1} as pair.
### 解题思路：
    use binay search to find the value pointed by the index is equal to the target value, then use while loop to extend to the left and right side
### 注意：
    None
### 复杂度：
    Time: O(LogN)
    Space: O(1)
### Code示例:
```Java
class Solution {
    
    public pair indexes(long v[], long x)
    {
        // Your code goes here
        int low = 0, high = v.length-1;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (v[mid] == x) {
                int left = mid, right = mid;
                while (left >= 0 && v[left] == x) {
                    left--;
                }
                while (right < v.length && v[right] == x) {
                    right++;
                }
                pair ans = new pair(left+1, right-1);
                return ans;
            } else if (v[mid] < x) {
                low = mid+1;
            } else {
                high = mid-1;
            }
        }
        
        return new pair(-1, -1);
        
    }
}
```
