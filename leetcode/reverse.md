## 问题分析： 
给定一个范围为 32 位 int 的整数，将其颠倒。


## 代码实现
```c
int reverse(int x) {
  long res = 0;
        while(x!=0){
            res = res * 10 + x % 10;
            x =x / 10;
        }
    if(res<-2147483648||res>2147483647)
        {
        res=0;
        }
        return res;
    
}
```
## 总结：

将数值采用溢出的方式，依次得到数据低位并将其作为新的数据高位。