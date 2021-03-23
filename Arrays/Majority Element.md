[Majority Element](https://practice.geeksforgeeks.org/problems/majority-element-1587115620/1)
tags: [array, easy] 
# Majority Element
### 题目大意：
    Given an array A of N elements. Find the majority element in the array. 
    A majority element in an array A of size N is an element that appears more than N/2 times in the array.
### 解题思路：
    Initialize a hashmap to store each element as key and record the frequncy of this key in this array as value
    then check each key in map, if the value associated with this key is larger than the half size, return this key

    if there is no key satisfied with the condition, just return -1
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(1)
### Code示例:
```Java
class Solution
{
    static int majorityElement(int a[], int size)
    {
        // your code here
        Map<Integer, Integer> map = new HashMap<>();
        
        for (int i : a) {
            map.put(i, map.getOrDefault(i, 0)+1);
        }
        
        for (Integer key : map.keySet()) {
            if (map.get(key) > size/2) return key;
        }
        
        return -1;
    }
}
```
