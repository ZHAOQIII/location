## 问题分析： 
判断一个整数是否是回文数。


## 代码实现
```c
bool isPalindrome(int x) {
    int t=x,res=0;
        if(x<0) {  
        return 0;  
    }    
    while(t) { 
        res=res*10+t%10;  
        t=t/10;  
    }  
    return x==res;  
}  
  
```
## 总结：

将数值颠倒，如果与原数相等，则为回文数。