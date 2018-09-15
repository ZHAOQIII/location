## 问题分析：
给定一个循环数组（最后一个元素的下一个元素是数组的第一个元素），输出每个元素的下一个更大元素。数字 x 的下一个更大的元素是按数组遍历顺序，这个数字之后的第一个比它更大的数，这意味着你应该循环地搜索它的下一个更大的数。如果不存在，则输出 -1。
```c
class Solution {
public:
    vector<int> nextGreaterElements(vector<int>& nums) {
        int n=nums.size();
        vector<int> res(n,-1);
        for(int i=0;i<n;++i)
        {
            for(int j=i+1;j<i+n;++j)
            {
                if(nums[j%n]>nums[i])
                {
                    res[i]=nums[j%n];
                    break;
                }
            }
        }
        return res;
    }
};
```
#总结
依次判断下一个数字是否大于当前数字。
