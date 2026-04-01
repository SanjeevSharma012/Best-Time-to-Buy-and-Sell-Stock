📈 Best Time to Buy and Sell Stock

This project contains a Java solution to find the maximum profit that can be achieved by buying and selling a stock once.

🚀 Problem Statement

You are given an array prices[] where:

prices[i] represents the price of a stock on day i
You can buy one stock and sell it later
Return the maximum profit possible
If no profit is possible, return 0
💡 Approach

We use a single-pass greedy approach:

Track the minimum price (buyPrice) seen so far
For each price:
Calculate potential profit
Update maximum profit if better
If current price is lower → update buyPrice
🧠 Algorithm
Initialize:
buyPrice = Integer.MAX_VALUE
maxProfit = 0
Traverse array:
If current price > buyPrice → calculate profit
Else → update buyPrice
Return maxProfit
🧾 Code
class Solution {
    public int maxProfit(int[] prices) {
        int buyPrice = Integer.MAX_VALUE;
        int MaxProfit = 0;

        for (int i = 0; i < prices.length; i++) {
            if (buyPrice < prices[i]) {
                int profit = prices[i] - buyPrice;
                MaxProfit = Math.max(MaxProfit, profit);
            } else {
                buyPrice = prices[i];
            }
        }
        return MaxProfit;
    }
}
⏱️ Complexity
Time Complexity: O(n) → Single traversal
Space Complexity: O(1) → No extra space used
📊 Example
Input:  [7, 1, 5, 3, 6, 4]
Output: 5

Explanation:
Buy at price = 1  
Sell at price = 6  
Profit = 6 - 1 = 5
🧪 Edge Cases
Prices always decreasing → return 0
Single element → return 0
Empty array → return 0
📌 Key Insights
Always buy at the lowest price before selling
Only one transaction is allowed
Greedy strategy ensures optimal solution
🏁 Conclusion

This solution efficiently finds the best profit using a simple and optimized approach. It’s a classic problem to understand greedy algorithms and array traversal techniques.

Author 
Sanjeev Sharma
