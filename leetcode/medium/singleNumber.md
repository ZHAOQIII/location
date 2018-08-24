## 问题分析： 
给定一个整数数组 nums，其中恰好有两个元素只出现一次，其余所有元素均出现两次。 找出只出现一次的那两个元素。
## 代码实现
```c
class Solution {
public:
    vector<int> singleNumber(vector<int>& nums) {
        vector<int>res;
       sort(nums.begin(),nums.end());
        if(nums[0]!=nums[1]){res.push_back(nums[0]);}
        for(int i=1;i<nums.size()-1;i++){
            if(nums[i]!=nums[i+1]&&nums[i]!=nums[i-1]){res.push_back(nums[i]);}
        }
            if(nums[nums.size()-1]!=nums[nums.size()-2]){res.push_back(nums[nums.size()-1]);}
        return res;
    }
};
```
## 总结：
可将数组排序，第一个不与第二个相等即可入栈，最后一个不与前一个相等可入栈。位于数组之间的，须与前一个不相等，且与后一个不相等才可入栈。
      
      