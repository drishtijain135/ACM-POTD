# POTD Day 16

## Problem
Implement a queue using two stacks.  
The queue should support standard operations: `push`, `pop`, `peek`, and `empty`.

## Approach
Use two stacks:
- `inStack` → for inserting elements  
- `outStack` → for removing elements  

### Logic:
- **Push:** Always push into `inStack`  
- **Pop/Peek:**  
  - If `outStack` is empty, transfer all elements from `inStack` to `outStack` (this reverses order)  
  - Then perform pop/peek from `outStack`  
- **Empty:** Check if both stacks are empty  

This ensures FIFO behavior using LIFO stacks.

## Solution
```cpp
class MyQueue {
public:
    stack<int> inStack;
    stack<int> outStack;

    MyQueue() {}

    void push(int x) {
        inStack.push(x);
    }

    int pop() {
        if (outStack.empty()) {
            while (!inStack.empty()) {
                outStack.push(inStack.top());
                inStack.pop();
            }
        }
        int val = outStack.top();
        outStack.pop();
        return val;
    }

    int peek() {
        if (outStack.empty()) {
            while (!inStack.empty()) {
                outStack.push(inStack.top());
                inStack.pop();
            }
        }
        return outStack.top();
    }

    bool empty() {
        return inStack.empty() && outStack.empty();
    }
};
```
## Screenshot
<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/94d3e2f7-77d7-4df2-8f93-55f35ea33713" />
