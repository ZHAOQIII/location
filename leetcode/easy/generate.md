## 问题分析： 
给定一个非负整数 numRows，生成杨辉三角的前 numRows 行。


## 代码实现
```c
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ret(numRows);
        for(int i=0; i<numRows; ++i) {
            ret[i].push_back(1);
            for(int j=1; j<i; ++j) 
                ret[i].push_back(ret[i-1][j-1] + ret[i-1][j]);
            if(i) ret[i].push_back(1);
        }
        return ret;
    }
};
```
## 总结：
第一行和第二行直接全赋值为1.其他的第i行(i>=0)，有ret[i][0]  = 1,ret[i][i] = 1;ret[i][j] = a[i-1][j-1]+a[i-1][j];