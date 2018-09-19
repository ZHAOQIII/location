## 问题分析：
给定一个只包含整数的有序数组，每个元素都会出现两次，唯有一个数只会出现一次，找出这个数。
## 代码实现
```c
class Solution {
public:
    int singleNonDuplicate(vector<int>& nums) {
      int len = nums.size();
        for(int i=0; i<len-2; i+=2){
            if(nums[i] != nums[i+1]){
                return nums[i];
            }
        }
        return nums[len-1];
    }
};
```
## 总结：
遍历数组，步长为2,如果当前值与下一个值不想等，则返回当前值。
