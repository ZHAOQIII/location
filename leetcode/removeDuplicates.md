## 问题分析： 
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。


## 代码实现
```c
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
    int i, j;  
        for(i = 0; i < nums.size(); i++){  
            for(j = i + 1; j < nums.size() && nums[i] == nums[j]; )
            {  
                nums.erase(nums.begin() + j);  
            }  
        }  
        return nums.size();  
    }
};
```
## 总结：
判断数组前后元素是否相同，如果相同，保留一个元素，删除一个元素，然后与下一个元素继续比较。如果不相同，保留前一个元素，比较后两个元素。