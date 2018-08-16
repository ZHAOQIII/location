## 问题分析： 
给定包含多个点的集合，从其中取三个点组成三角形，返回能组成的最大三角形的面积。
## 代码实现
```c
class Solution {
public:
    double largestTriangleArea(vector<vector<int>>& points) {   
    int n=points.size();
    double res=0;
    double area;
    for(int i=0;i<n;i++)
    {
        for(int j=i+1;j<n;j++)
        {
            for(int k=j+1;k<n;k++)
            {
                area=0.5*abs(points[i][0]*(points[j][1]-points[k][1])+points[j][0]*(points[k][1]-points[i][1])+points[k][0]*(points[i][1]-points[j][1]));
                res=max(res,area);
            }
        }
    }
    return res;
   
    }
};
```
## 总结：
如果已知三个点为(x1,y1)，(x2,y2)，(x3,y3)，面积为A= 1/2 * [ x1(y2-y3) + x2(y3-y1) + x3(y1-y2) ]。依次遍历，寻找最大值。
      
      
      