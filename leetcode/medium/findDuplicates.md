## 问题分析： 
给定一个整数数组 a，其中1 ≤ a[i] ≤ n （n为数组长度）, 其中有些元素出现两次而其他元素出现一次。

找到所有出现两次的元素。

你可以不用到任何额外空间并在O(n)时间复杂度内解决这个问题吗？
## 代码实现
```c
class Solution {
public:
    vector<int> findDuplicates(vector<int>& nums) {
     int m=nums.size(),n;
     vector<int> res;
    sort(nums.begin(),nums.end());
     for(int i=0;i<m;i++)
        if(nums[i]==nums[i+1]) {ans.push_back(nums[i]);i++;}
     return res;
    }
};
```
## 总结：
先将数组排序，如果出现前后两个数值相等，则将该数值入栈，并且i=i+2，否则i++，继续遍历。
      
      