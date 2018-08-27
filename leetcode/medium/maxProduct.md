## 问题分析： 
给定一个整数数组 nums ，找出一个序列中乘积最大的连续子序列（该序列至少包含一个数）。

## 代码实现
```c
class Solution {
public:
    int maxProduct(vector<int>& nums) {
      int max=1,n=nums.size(),max1;
        for(int i=0;i<n;i++){
            max=max*nums[i];
        }
        for(int j=0;j<n;j++){
         max1=nums[j];if(max1>max){max=max1;} 
            for(int k=j+1;k<n;k++){
                max1=max1*nums[k];
                if(max1>max){max=max1;}
            }
        }
        return max;
    }
};
```
## 总结：
依次遍历数组作为基准，然后遍历相乘基准后面的数值，直到得到最大值.
      
      