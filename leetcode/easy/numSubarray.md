## 问题分析： 
给定一个正整数数组 nums。

找出该数组内乘积小于 k 的连续的子数组的个数。
## 代码实现
```c
class Solution {
public:
    int numSubarrayProductLessThanK(vector<int>& nums, int k) {
       if(k<=1) return 0;
        int ret = 0;
        int p = 1;
        int left = 0;
        for(int i = 0;i<nums.size();++i) {
            p*=nums[i];
            while(left<=i&&p>=k) p/=nums[left++];
            ret+= i-left+1;
        }
        return ret;
    }
};
```
## 总结
如果当前值小于k，以当前值为基准，依次向后相乘，积小于k则ret++。
      