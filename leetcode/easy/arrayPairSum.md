## 问题分析： 
给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。
## 代码实现
```c
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
      sort(nums.begin(),nums.end());
        int n=nums.size(),i,sum=0;
        for(i=0;i<n;i+=2){
            sum=sum+nums[i];
        }
        return sum;
    }
};
```
## 总结：
要想得到n个小数组中较小值的总和最大，先将数组排序，每两个数值中的较小值相加，即为所求。