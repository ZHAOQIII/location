## 问题分析： 
给定一个已按照升序排列 的有序数组，找到两个数使得它们相加之和等于目标数。

函数应该返回这两个下标值 index1 和 index2，其中 index1 必须小于 index2。


## 代码实现
```c
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
     int l = 0, r = numbers.size() - 1;
        while (l < r) { 
            if (numbers[l] + numbers[r] == target)
                return {l + 1, r + 1};
            else if (numbers[l] + numbers[r] > target)
                r--;  
            else l++;
        }
        return {0, 0};
    }
};
```
## 总结：
用两个指针从两边往中间找，如果numbers[l] + numbers[r] ＝＝ target 就返回l r组成的数组加1， 因为l r是从0开始的index。 如果和比target大，那就是现在的numbers[r]大了，用r--选择向左一位的元素，l同理。循环直至找到最终结果。
