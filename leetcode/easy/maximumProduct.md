## 问题分析： 
给定一个整型数组，在数组中找出由三个数组成的最大乘积，并输出这个乘积。
## 代码实现
```c
class Solution {
public:
    int maximumProduct(vector<int>& nums) {
        int mul,n=nums.size(),mul1;
        sort(nums.begin(),nums.end());
        if(nums[n-1]<0){mul=nums[n-1]*nums[n-2]*nums[n-3];}
        if(nums[0]>=0){mul=nums[n-1]*nums[n-2]*nums[n-3];}
        if(nums[0]<0 &&nums[n-1]>0){
            mul=nums[n-1]*nums[n-2]*nums[n-3];
            mul1=nums[n-1]*nums[0]*nums[1];
            if(mul<mul1){mul=mul1;}
        }
        return mul;
    }
};
```
## 总结：
首先将数组排序，最大乘积为数组最后三个数值相乘，或者最开始两个数值与最后一个数值相乘，最后找出它们的较大值，即为所求最大乘积。