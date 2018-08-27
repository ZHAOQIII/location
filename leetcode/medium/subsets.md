## 问题分析： 
给定一组不含重复元素的整数数组 nums，返回该数组所有可能的子集（幂集）。
## 代码实现
```c
class Solution {
public:
    vector<vector<int>> subsets(vector<int>& nums) {
     vector<vector<int> > res(1);
          sort(nums.begin(), nums.end());
          for (int i = 0; i < nums.size(); ++i) {
             int size = res.size();
              for (int j = 0; j < size; ++j) {
                 res.push_back(res[j]);               
                  res.back().push_back(nums[i]);
             }
        }
         return res;   
    }
};
```
## 总结：
最开始是空集，现在要处理1，就在空集上加1，为[1]，得到[]和[1]，下面来处理2，在之前的子集基础上，每个都加个2，可以分别得到[2]，[1, 2]，那么现在所有的子集合为[], [1], [2], [1, 2]，同理处理3的情况可得[3], [1, 3], [2, 3], [1, 2, 3], 再加上之前的子集就是所有的子集合了。。
      
      