[Find missing in second array](https://practice.geeksforgeeks.org/problems/in-first-but-second5423/1)
# Find missing in second array
### 题目大意：
    Given two arrays A and B contains integers of size N and M, the task is to find numbers which are present in the first array, but not present in the second array.
### 解题思路：
    first add all elements in array B into set, then check each element in array A, if the current element is not in the set, it satisfies the condition, we put in the answer list
### 注意：
    None
### 复杂度：
    Time:O(N+M)
    Space: O(M)
### Code示例:
```Java
class Solution
{
    ArrayList<Long> findMissing(long A[], long B[], int N, int M)
    {
         ArrayList<Long> ans = new ArrayList<>();
         Set<Long> setB = new HashSet<>();
         for (long b : B) {
             if (!setB.contains(b)) {
                 setB.add(b);
             }
         }
         
         for (long a : A) {
             if (!setB.contains(a)) {
                 ans.add(a);
             }
         }
         
         return ans;
    }
}
```
