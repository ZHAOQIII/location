## 问题分析： 
如果一个矩阵的每一方向由左上到右下的对角线上具有相同元素，那么这个矩阵是托普利茨矩阵。

给定一个 M x N 的矩阵，当且仅当它是托普利茨矩阵时返回 True。
## 代码实现
```c
class Solution {
public:
    bool isToeplitzMatrix(vector<vector<int>>& matrix) {
     for(int i =1;i<matrix.size();i++){
            for(int j = 1;j<matrix[i].size();j++){
                if(matrix[i][j]!=matrix[i-1][j-1])
                    return false;
            }
        }
        return true;   
    }
};
```
## 总结：
一个MxN的矩阵，每个对角线相等，即矩阵每个元素都与其左上角的元素相等。
      
      
      