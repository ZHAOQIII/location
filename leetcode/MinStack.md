## 问题分析： 
设计一个支持 push，pop，top 操作，并能在常数时间内检索到最小元素的栈。

push(x) -- 将元素 x 推入栈中。

pop() -- 删除栈顶的元素。

top() -- 获取栈顶元素。

getMin() -- 检索栈中的最小元素。

## 代码实现
```c
class MinStack {
public:
    /** initialize your data structure here. */
    MinStack() {
        
    }
    
    void push(int x) {
      stk.push(x);
        if(sm.empty())
        {
            sm.push(x);
        }
        else if(sm.top()>=x)
        {
            sm.push(x);
        }
        else
        {
            sm.push(sm.top());
        }   
    }
    
    void pop() {
      stk.pop();
        sm.pop();   
    }
    
    int top() {
    return stk.top();    
    }
    
    int getMin() {
     return sm.top();    
    }
    private:
    stack<int> stk;
    stack<int> sm;
};

```
