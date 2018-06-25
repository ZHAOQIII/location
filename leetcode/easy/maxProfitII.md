## 问题分析： 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

设计一个算法来计算你所能获取的最大利润。你可以尽可能地完成更多的交易（多次买卖一支股票）。

## 代码实现
```c
class Solution {
public:
    int maxProfit(vector<int>& prices) {
      if(prices.size() ==0)  return 0;
        int maxProfit = 0;
        int curMin = prices[0];
        for(int i= 1 ; i<prices.size(); i++){
            if (prices[i] > curMin) {
                maxProfit += prices[i] - curMin;
                curMin = prices[i];
            } else {
                curMin = prices[i];
            }
        }
        return maxProfit;  
    }
};
```
## 总结：
从第一个元素开始遍历至最后一个元素；
若下一个元素比当前元素大，那么就抛售；并以下一个元素的价钱买入，同时累加利润；
若下一个元素比当前元素小，那么就以下一个元素的价钱买入（若连续出现递减的情况，那么最后的买入价格是最后那个最小的元素）；