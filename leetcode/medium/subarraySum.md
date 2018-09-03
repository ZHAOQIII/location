## 问题分析： 
给定一个整数数组和一个整数 k，你需要找到该数组中和为 k 的连续的子数组的个数。
## 代码实现
```c
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
     int n=nums.size(),i,j,count=0,sum=0;
        for(i=0;i<n;i++){
            for(j=i;j<n;j++){
                sum=sum+nums[j];
                if(sum==k){count++;}
            }
                sum=0;
        }
        return count;
    }
};
```
## 总结：
依次遍历数组，以i为基准，向后遍历，当和为k，则个数加1。
      
      