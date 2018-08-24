## 问题分析： 
给定长度为 n 的整数数组 nums，其中 n > 1，返回输出数组 output ，其中 output[i] 等于 nums 中除 nums[i] 之外其余各元素的乘积。
## 代码实现
```c
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        vector<int>res;
      int count = 0,pro = 1;
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] == 0)  {count++;}
            else  {pro *= nums[i];}
        }       
        if (count == 1) {
            for (int i = 0; i < nums.size(); i++) {
                if (nums[i] == 0) {res.push_back(pro);}
                else {res.push_back(0);}
            }
        }
        else if (count >= 2) {
         for(int i=0;i<nums.size();i++){
             res.push_back(0);
         }
        }
        else {
            for (int i = 0;i < nums.size(); i++)
                res.push_back(pro / nums[i]);}
            return res;
    }
};
```
## 总结：
求除自身以外其余各元素的乘积，可以求所有元素的乘积，然后除以自身即可。但是得考虑0的特殊情况，当有一个零时，除零位置以外，其余皆为0，当有两个及以上0，输出数组皆为0。
      
      