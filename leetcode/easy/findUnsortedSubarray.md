## 问题分析： 
给定一个整数数组，你需要寻找一个连续的子数组，如果对这个子数组进行升序排序，那么整个数组都会变为升序排序。

你找到的子数组应是最短的，请输出它的长度。
## 代码实现
```c
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
        vector<int> s=nums;
     int n=nums.size(),i,j,k;
        sort(s.begin(),s.end());
        for( i=0;i<n;i++){
            if(nums[i]!=s[i]) {break;}  
        }
       for( j=n-1;j>i;j--){
            if(nums[j]!=s[j]) break;   
        } 
       return j-i+1;
    }
};
```
## 总结：
新命名一个与原数组相等的数组，然后对该数组排序，两个数组分别从左从右比较，中间的数组即为需要排序的数组。