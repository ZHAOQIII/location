## 问题分析： 
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。


## 代码实现
```c
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
      int sum = 0;    
        int max = nums[0];    
        for(int i = 0; i != nums.size(); i++){    
            sum = nums[i];    
            if(max < sum)    
                max = sum;    
            for(int j = i+1; j != nums.size(); j++) {    
                sum += nums[j];     
                if(max < sum)    
                    max = sum;    
            }    
        }     
        return max;    
    }  
};  
```
## 总结：

以数组的第一个数值为基准，加上下一个数值，如果变小，则舍弃返回前一个数据。如果变大，则将当前数据作为新的基准。