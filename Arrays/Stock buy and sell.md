[Stock buy and sell](https://practice.geeksforgeeks.org/problems/stock-buy-and-sell-1587115621/1)
tags: [medium, array] 
# Stock buy and sell
### 题目大意：
    The cost of stock on each day is given in an array A[] of size N. Find all the days on which you buy and sell the stock so that in between those days your profit is maximum.
    Note: There may be multiple possible solutions. Print any one of them.
### 解题思路：
    first, this question is related with linear check, we can use while loop to check each element.
    first we find the index of lower price that we can buy, then we find the index of higher price to sell, then put the index that we record about buy and sell into profit object

    finally we add each object as ArrayList into nested ArrayList and return.
### 注意：
    None
### 复杂度：
    Time: O(N)
    Space: O(N)
### Code示例:
```Java
class Profit {
    int buy;
    int sell;
    public Profit(int buy, int sell) {
        this.buy = buy;
        this.sell = sell;
    }
}

class Solution{
    //Function to find the days of buying and selling stock for max profit.
    ArrayList<ArrayList<Integer>> stockBuySell(int A[], int n) {
        // code here
        ArrayList<ArrayList<Integer>> ans = new ArrayList<ArrayList<Integer>>();
        if (n == 1) return ans;
        List<Profit> p = new ArrayList<>();
        int i = 0, cnt = 0;
        
        while (i < n-1) {
            while (i < n-1 && A[i+1] <= A[i]) {
                i++;
            }
            
            if (i == n-1) break;
            
            int buy = i;
            i++;
            
            
            while (i < n && A[i] >= A[i-1]) {
                i++;
            }
            int sell = i-1;
            
            Profit profit = new Profit(buy, sell);
            p.add(profit);
            cnt++;
        }
        
        if (cnt == 0) return ans;
        else {
            for (int j = 0; j < p.size(); j++) {
                ans.add(new ArrayList<>());
                ans.get(j).add(p.get(j).buy);
                ans.get(j).add(p.get(j).sell);
            }
        }
        
        return ans;
    }
}
```
