## 问题分析： 
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。

## 代码实现
```c
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
      k = k%nums.size();
        std::reverse(nums.begin(),nums.end());
        std::reverse(nums.begin(),nums.begin()+k);
        std::reverse(nums.begin()+k,nums.end());
        
        return;
        
    }
};
```
## 总结：
分三步进行：

1.将整个数组翻转。

2.再将0 - k-1范围内的元素进行翻转。

3.将 k-nums.size()范围内的元素进行翻转。
