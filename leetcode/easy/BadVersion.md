## 问题分析： 
你是产品经理，目前正在带领一个团队开发新的产品。不幸的是，你的产品的最新版本没有通过质量检测。由于每个版本都是基于之前的版本开发的，所以错误的版本之后的所有版本都是错的。

假设你有 n 个版本 [1, 2, ..., n]，你想找出导致之后所有版本出错的第一个错误的版本。

你可以通过调用 bool isBadVersion(version) 接口来判断版本号 version 是否在单元测试中出错。实现一个函数来查找第一个错误的版本。你应该尽量减少对调用 API 的次数。


## 代码实现
```c
bool isBadVersion(int version);

class Solution {
public:
    int firstBadVersion(int n) {    
    if(n <= 0)  return 0;  
    int low = 1;  
    int high = n;  
    int mid;  
    bool value;  
    while(low <= high) {  
        mid = (low+high)/2;  
        value = isBadVersion(mid);  
        if(value) {      
            high = mid - 1;  
        }  
        else {  
            low = mid + 1;  
        }  
              
    }  
    return low;   
    }
};
```
## 总结：
因为要尽可能少的调用函数，所以采用二分法来查找错误的版本。