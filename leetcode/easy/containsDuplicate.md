## 问题分析： 
给定一个整数数组，判断是否存在重复元素。

如果任何值在数组中出现至少两次，函数返回 true。如果数组中每个元素都不相同，则返回 false。


## 代码实现
```c
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        int len=nums.size();
       for(int i=0;i<len;i++)
       {
           for(int j=i+1;j<len;j++)
           {
               if(nums[i]==nums[j])
               {
                    return true;
               }
           }
       }
        return false;
    }
};
```
## 总结：
以当前数值作为目标值遍历数组剩余部分，如果出现与当前值相等的数值，则返回true，否则以下一个数值作为目标值，以此类推。