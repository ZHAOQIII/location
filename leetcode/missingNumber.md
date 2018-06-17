## 问题分析： 
给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。


## 代码实现
```c
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int i,n;
        n=nums.size();
         sort(nums.begin(), nums.end());
        for(i=0;i<=n;i++){
            if(nums[i]==i) continue;
            else return i;
        }
    
    }
};
```
## 总结：
先对序列排序，在依次比较，相等则继续比较下一个，不相等则返回当前值。