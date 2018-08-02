## 问题分析： 
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。

移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
## 代码实现
```c
class Solution {
public:
    bool judgeCircle(string moves) {
        int i,j,k,l,n=moves.size();
        i=j=k=l=0;
        for(int a=0;a<n;a++){
            if(moves[a]=='R') {i++;}
            if(moves[a]=='L') {j++;}
            if(moves[a]=='U') {k++;}
            if(moves[a]=='D') {l++;}
        }
       if(i==j &&k==l) {return true;}
        return false;
    }
};
```
## 总结：
分别统计 R（右），L（左），U（上）和 D（下）出现的次数，当R次数=L次数，同时U次数=D次数，即可返回原来的位置。