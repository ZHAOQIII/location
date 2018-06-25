## 问题分析： 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在众数。


## 代码实现
```c
class Solution {
public:
    int majorityElement(vector<int>& nums) {
     int count=0;
        int res=nums[0];
        for(int i=0;i<nums.size();i++)
        {
            if(count==0||nums[i]==res)
            {
                count++;
                res=nums[i];
            }
            else
                count--;
        }
        return res;
    }   
};
```
## 总结：
每次从数组中找出一对不同的元素，将它们从数组中删除，直到遍历完整个数组。由于众数出现次数超过一半的元素，所以遍历完数组后数组中一定会存在至少一个元素。 