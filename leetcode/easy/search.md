## 问题分析： 
给定一个 n 个元素有序的（升序）整型数组 nums 和一个目标值 target  ，写一个函数搜索 nums 中的 target，如果目标值存在返回下标，否则返回 -1。
## 代码实现
```c
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int left = 0, right = nums.size() - 1;
        while(left <= right) {
            int mid = left + (right - left) / 2;
            if(nums[mid] == target) {
                return mid;
            }
            if(nums[mid] < target) {
                left += 1;
            }
            if(nums[mid] > target) {
                right -= 1;
            }
        }
        return -1;
    }
};
```
## 总结：
定义两个指针，分别指向数组末端和开端，采用二分查找法，当中心值大于target是，中心值向开端移动，right--，反之亦然。
      
      
      