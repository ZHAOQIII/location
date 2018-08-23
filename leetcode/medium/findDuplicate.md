## 问题分析： 
给定一个包含 n + 1 个整数的数组 nums，其数字都在 1 到 n 之间（包括 1 和 n），可知至少存在一个重复的整数。假设只有一个重复的整数，找出这个重复的数。
## 代码实现
```c
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
      sort(nums.begin(),nums.end());
        int i;
        for(i=0;i<nums.size();i++){
            if(nums[i]==nums[i+1]){ break;
            }
        }
        return nums[i];
    }
};
```
## 总结：
将数组排序，如果出现重复的数，则会出现前后两个数值相等，返回当前值即可。
      
      