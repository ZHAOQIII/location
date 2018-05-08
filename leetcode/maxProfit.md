## 问题分析： 
给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。


## 代码实现
```c
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int max = 0;
        int n = prices.size();
        if(n<=1) return max;
        for(int i=0;i<n;i++){
            for(int j = i+1;j<n;j++){
                max = max>(prices[j]-prices[i])?max:(prices[j]-prices[i]);
            }
        }
        return max;
    }
};
```
## 总结：
假如在第i天买入股票，找出第i+1到最后一天的对于第i天利润的最大值，遍历一遍，找出整个数组的最大值，即为最大利润。