## 问题分析： 
我们把符合下列属性的数组 A 称作山脉：

A.length >= 3  
存在 0 < i < A.length - 1 使得A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1]  
给定一个确定为山脉的数组，返回任何满足 A[0] < A[1] < ... A[i-1] < A[i] > A[i+1] > ... > A[A.length - 1] 的 i 的值。

 
## 代码实现
```c
class Solution {
public:
    int peakIndexInMountainArray(vector<int>& A) {
        int i;
        for(i=1;i<A.size();i++){
            if(A[i]>A[i-1] & A[i]>A[i+1]) break;
        }
        return i; 
    }
};
```
## 总结：
找到山峰，即转折点，大于前一个数且大于后一个数。
      
      
      