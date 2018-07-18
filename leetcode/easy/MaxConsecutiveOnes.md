## 问题分析： 
给定一个二进制数组， 计算其中最大连续1的个数。
## 代码实现
```c
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
   int max = 0;
        int curr = 0;
        for (int i = 0; i < nums.size(); ++i)
        {
            if (nums[i] == 1) {
                curr++;
            } else {
                if (max < curr)
                    max = curr;
                curr = 0;
            }
        }
        return max > curr ? max : curr;
        }
};
```
## 总结：
当数组第i位为1，进行累加，遍历至下一位为0，则打断，并与上一个1的个数最大值比较大小。