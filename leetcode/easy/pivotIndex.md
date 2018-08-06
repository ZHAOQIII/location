## 问题分析： 
给定一个整数类型的数组 nums，请编写一个能够返回数组“中心索引”的方法。

我们是这样定义数组中心索引的：数组中心索引的左侧所有元素相加的和等于右侧所有元素相加的和。

如果数组不存在中心索引，那么我们应该返回 -1。如果数组有多个中心索引，那么我们应该返回最靠近左边的那一个。
## 代码实现
```c
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
      int n=nums.size(),i,sum1,sum2;
        sum1=sum2=0;
        if(n==1) return true;
        for(i=0;i<n;i++){
            for(int j=0;j<i;j++){
                sum1=sum1+nums[j];
            }
            for(int k=i+1;k<n;k++){
                sum2=sum2+nums[k];
            }
            if(sum1==sum2){return i;}
            else sum1=sum2=0;
        }
        return -1;
    }
};
```
## 总结：
从第一个开始，将它左边相加，然后再将它右边相加，比较两边是否相等，如果相等则返回当前索引，否则比较下一个值的左边和右边。
      
      
      