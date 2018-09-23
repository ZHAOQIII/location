## 问题分析：
给定一个包含非负数的数组和一个目标整数 k，编写一个函数来判断该数组是否含有连续的子数组，其大小至少为 2，总和为 k 的倍数，即总和为 n*k，其中 n 也是一个整数。
## 代码实现
```c
class Solution {
public:
    bool checkSubarraySum(vector<int>& nums, int k) {
      int sum,n=nums.size();
        for(int i=0;i<n-1;i++){
            sum=nums[i];
            for(int j=i+1;j<n;j++){
                sum=sum+nums[j];
                if(k==0){if(sum==0) return true;}
                else{if(sum%k==0){return true;}}
            }
        }
        return false;
    }
};```
## 总结：
依次累加，判断和是否为k的倍数。应特别注意k=0的情况。
