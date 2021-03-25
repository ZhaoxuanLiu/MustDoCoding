[Binary Search in forest ](https://practice.geeksforgeeks.org/problems/ffd66b6a0bf7cefb9987fa455974b6ea5695709e/1/)
# Binary Search in forest 
### 题目大意：
    There are n tree in a forest. Heights of the trees is stored in array tree[ ]. If ith tree is cut at height h, the wood obtained is tree[i]-h, given that tree[i]>h. If total wood needed is k (not less, neither more) find the height at which every tree should be cut (all trees have to be cut at the same height).
### 解题思路：
    first find the maximum height then find the middle value between lowest tree height and highest tree height
    then use binary search to find the the current middle value of tree height can get k pieces wood
    Also we need to create a helper function to calculate the number of wood we can get if we cut at the current mid value of tree height.
### 注意：
    None
### 复杂度：
    Time:
    Space: 
### Code示例:
```Java
class solver
{
    static int find_height(int tree[], int n, int k)
    {
        // code here
        int low = 0, high = 0;
        for (int i = 0; i < n; i++) {
            if (tree[i] > high) {
                high = tree[i];
            }
        }
        
        while (low <= high) {
            int mid = low + (high - low) / 2;
            
            int val = helper(tree, n, mid);
            
            if (val == k) return mid;
            else if (val > k) low = mid + 1;
            else high = mid - 1;
        }
        
        return -1;
    }
    
    
    static int helper(int[] tree, int n, int h) {
        int ans = 0;
        for (int i = 0; i < n; i++) {
            if (tree[i] > h) {
                ans += tree[i] - h;
            }
        }
        return ans;
    }
        
}
```
