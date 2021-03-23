[Plus One](https://practice.geeksforgeeks.org/problems/plus-one/1/#)
tags: [array, easy] 
# Plus One
### 题目大意：
    Given a non-negative number represented as a list of digits, 
    add 1 to the number (increment the number represented by the digits). 
    The digits are stored such that the most significant digit is first element of array.
### 解题思路：
    Since we need to return an arraylist, we can directly change in the given array
    we can check from the last digit, if the digit is smaller than 9,
    we add 1 in this digit and return this arr,
    if the digit is not smaller than 9, we can set current digit as 0, and let index move
    to second last digit.
    when finish checking all digits, we let arr add one more 0 in this arr, and set the 
    first element as 1, finally return arr
### 注意：
    None
### 复杂度：
    Time:O(N)
    Space: O(1)
### Code示例:
```Java
//User function Template for Java

class Solution {
    static ArrayList<Integer> increment(ArrayList<Integer> arr, int N) {
        // code here
    
        int i = N-1;
        while (i >= 0) {
            if (arr.get(i) < 9) {
                int tmp = arr.get(i);
                tmp++;
                arr.set(i, tmp);
                return arr;
            } 
            
            arr.set(i, 0);
            i--;
        }
        
        arr.add(0);
        arr.set(0, 1);
        
        return arr;
    }
}
```
