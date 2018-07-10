## 问题分析： 


给定一个长度为 n 的非空整数数组，找到让数组所有元素相等的最小移动次数。每次移动可以使 n - 1 个元素增加 1。

## 代码实现
```c
class Solution {
public:
    int minMoves(vector<int>& nums) {
          int n = nums.size();
        int sum = nums[0];
        int min = nums[0];
        for(int i = 1; i < n; ++i){
            min = (min < nums[i])?min:nums[i];
            sum += nums[i];
        }
        return sum - n*min;    
    }
};
```
## 总结：
首先观察，数组最开始总和记为sum，然后观察最后的数组一定是所有元素都相同。不管如何操作数组，数组最开始的最小元素一定是不断累加的，而每次累加的时候，数组的总和增加为数组规模减一sum + m * (n - 1) = min + m，m是数组操作的次数。