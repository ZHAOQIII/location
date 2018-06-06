## 问题分析： 
给定一个整数数组和一个整数 k，判断数组中是否存在两个不同的索引 i 和 j，使得 nums [i] = nums [j]，并且 i 和 j 的差的绝对值最大为 k。


## 代码实现
```c
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
         unordered_map<int ,int> maps;
        int length=nums.size();
        for(int i=0;i<length;i++)
        {
            if(maps.count(nums[i]))
            {
                if((i-maps[nums[i]])<=k) 
                    return true;
            }
            maps[nums[i]]=i;
        }
        return false;
    }       
};
```
## 总结：
以当前值作为目标值，寻找是否有与当前值相等的值，如果有，则判断两者距离是否小于等于k。如果没有，则将下一个数值作为当前值，以此类推。