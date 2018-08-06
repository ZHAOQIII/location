## 问题分析： 
给定一个只包含小写字母的有序数组letters 和一个目标字母 target，寻找有序数组里面比目标字母大的最小字母。

数组里字母的顺序是循环的。举个例子，如果目标字母target = 'z' 并且有序数组为 letters = ['a', 'b']，则答案返回 'a'。
## 代码实现
```c
class Solution {
public:
    char nextGreatestLetter(vector<char>& letters, char target) {
        char min;
        int n=letters.size();
        if(target<letters[n-1]) {
            min=letters[n-1];
            for(int i=0;i<n;i++){          
               if(letters[i]>target&&min>letters[i]) {min=letters[i];}}}
         else min=letters[0];
        
        return min;
    }
};
```
## 总结：
因为数组是有序的，所以当最后一个字母小于或等于目标字母时，那比目标字母大的最小字母即为第一个字母。反之则依次遍历找出大于目标字母的最小字母。
      
      
      