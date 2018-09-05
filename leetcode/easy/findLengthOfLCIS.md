## 问题分析： 
给定一个未经排序的整数数组，找到最长且连续的的递增序列。
## 代码实现
```c
class Solution {
public:
    int findLengthOfLCIS(vector<int>& nums) {
       int n=nums.size(),max=1,count=1,i,j;
        if(n==0){return 0;}
            for(j=0;j<n-1;j++){
                if(nums[j+1]>nums[j]){count++;}
                else {if(count>max){max=count;}
                      count=1;
            }
            }
            if(max<count){max=count;}
        return max;
    }
};
```
## 总结
依次遍历数组，当前一个小于后一个，计数加一，否则计数归零，向后遍历。
      