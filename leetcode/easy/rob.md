## 问题分析： 
你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。


## 代码实现
```c
class Solution {
public:
    int rob(vector<int>& nums) {
        if(nums.empty())
            return 0;
        if(nums.size()==1)
            return nums[0];
        
        int minV = nums[0];
        int maxV = max(nums[0],nums[1]);
        
        for(int i = 2;i<nums.size();i++)
        {
            int tempV = maxV;
            maxV = max(minV+nums[i],maxV);
            minV = tempV;
        }
        return maxV;
    }
};
```
## 总结：
采用动态规划，利用状态转移方程，找到打劫到第i间房屋时累计取得的金钱最大值。。