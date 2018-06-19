## 问题分析： 

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

## 代码实现
```c
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
   int n = nums.size();
        int a = 0 ;
        for(int i = 0;i < n;i++){
            if(nums[i]!=0){
                nums[a] = nums[i];
                a++;
            }
        }
        for(int i = a;i < n; ++i){
            nums[i] = 0;
        }  
    }
};
```
## 总结：
首先遍历数组，删除零，然后再在数组后面补零。
