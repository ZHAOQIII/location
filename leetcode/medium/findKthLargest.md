## 问题分析：
在未排序的数组中找到第 k 个最大的元素。请注意，你需要找的是数组排序后的第 k 个最大的元素，而不是第 k 个不同的元素。
## 代码实现
```c
class Solution {
public:
    int findKthLargest(vector<int>& nums, int k) {
      int n=nums.size();
        sort(nums.begin(),nums.end());
        return nums[n-k];
    }
};
```
## 总结：
对数组排序，从后往前k个即为第k大元素。
