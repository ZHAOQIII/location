## 问题分析： 
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。

## 代码实现
```c
class Solution {
public:
    int thirdMax(vector<int>& nums) {
     
        int res;
        sort(nums.begin(),nums.end());
        vector<int>::iterator iter = unique(nums.begin(), nums.end());
        nums.erase(iter,nums.end());
        int size = nums.size();
        if(size < 3)
            return res = nums.back();
        else 
            return res = nums[size - 3];
       
    }
};

```
## 总结：
首先将数组排序，然后去除重复，找到第三大的数。