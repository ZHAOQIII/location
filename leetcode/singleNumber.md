## 问题分析： 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。


## 代码实现
```c
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int i,j,k;
        k=nums.size();
        for(i=0;i<k;i++)
        {
            for(j=0;j<k;j++)
            {
                if(nums[i]==nums[j] && i!=j)
                    break;
            }
            if(j == k)
                return nums[i];
        }
        return nums[i];
    }
};
```
## 总结：
以第i个数据为基点，遍历找到其他数值等于第i个数据，如果能找到则继续遍历，如果不能则输出第i个数据。