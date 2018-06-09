## 问题分析： 
使用栈实现队列的下列操作：

push(x) -- 将一个元素放入队列的尾部。
pop() -- 从队列首部移除元素。
peek() -- 返回队列首部的元素。
empty() -- 返回队列是否为空。

## 代码实现
```c
class MyQueue {
public:
    /** Initialize your data structure here. */
    stack<int> s;
    MyQueue() {
       
    }
    
    /** Push element x to the back of queue. */
    void push(int x) {
    if(s.empty()) 
        {
            s.push(x);
            return ;
        }
        int tmp = pop();
        push(x);
        s.push(tmp);
    }
    
    /** Removes the element from in front of queue and returns that element. */
    int pop() {
    int res = s.top();
        s.pop();
        return res;
    }
    
    /** Get the front element. */
    int peek() {
      return s.top();
    }
    
    /** Returns whether the queue is empty. */
    bool empty() {
      return s.empty();}
};
```
## 总结：
基于栈先进后出，队列先进先出的特点，利用两个栈来实现队列的功能。