# POTD Day 17

## Problem
Implement a stack using a single queue.  
The stack should support standard operations: `push`, `pop`, `top`, and `empty`.

## Approach
Use one queue to simulate stack behavior (LIFO):

### Logic:
- **Push:**  
  - Push the element into the queue  
  - Rotate the queue (move previous elements to back) so the new element comes to the front  

- **Pop:**  
  - Remove the front element (acts as top of stack)  

- **Top:**  
  - Return the front element  

- **Empty:**  
  - Check if queue is empty  

This ensures the most recently added element is always at the front.

## Solution
```cpp
class MyStack {
public:
    queue<int> q;

    MyStack() {}

    void push(int x) {
        q.push(x);
        int size = q.size();

        // Rotate elements
        for (int i = 0; i < size - 1; i++) {
            q.push(q.front());
            q.pop();
        }
    }

    int pop() {
        int val = q.front();
        q.pop();
        return val;
    }

    int top() {
        return q.front();
    }

    bool empty() {
        return q.empty();
    }
};
```

## Screenshot 
<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/90e13bd4-5b91-42e8-bae7-4b0a4d2c9e1d" />
