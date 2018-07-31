## 问题分析： 
给定 n 个整数，找出平均数最大且长度为 k 的连续子数组，并输出该最大平均数。
## 代码实现
```c
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        int size = nums.size();
        double mean,maxmean;
        double sum=0.0;
        for(int i=0;i<=size-k;++i)
        {
            for(int j=i;j<i+k;++j)
            {
                sum+=nums[j];
            }
            mean=sum/k;
            sum=0;
            if(i==0)
            {
                maxmean=mean;
                continue;
            }
            if(mean>maxmean)
            {
                maxmean=mean;
            }
        }
        
        return maxmean;
    }
};
```
## 总结：
采用两个for循环，每次遍历k个连续整数相加，然后求平均值，依次比较，寻找最大的平均值。