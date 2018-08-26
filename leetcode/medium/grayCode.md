## 问题分析： 
格雷编码是一个二进制数字系统，在该系统中，两个连续的数值仅有一个位数的差异。

给定一个代表编码总位数的非负整数 n，打印其格雷编码序列。格雷编码序列必须以 0 开头。
## 代码实现
```c
class Solution {
public:
    vector<int> grayCode(int n) {
     vector<int> result(1);
        for(int i=0;i<n;i++)
        {
                for(int j=result.size()-1;j>=0;j--)
                {
                   result.push_back((1<<i)+result[j]);
                }
        }
        return result;   
    }
};
```
## 总结：
已知n=k，那么n=k+1的结果包括对n=k的结果左边补零，即保存不变，然后逆序遍历n=k的结果左边补1即可。
      
      