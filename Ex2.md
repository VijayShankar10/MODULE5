# Ex.No:2  
# Ex.Name: Insert float elements into Stack ADT using STL and display  

## Date:  

## Aim:  
To read `n` float elements, push them onto an STL `stack<float>`, print the stack size, and then display elements in LIFO order.  

## Algorithm:  
1. Start the program.  
2. Read integer `n` (count of elements).  
3. Push all float values onto `stack<float>`.  
4. Display the size of the stack.  
5. Pop elements from the stack one by one and display them.  
6. Stop the program.  

## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int n; 
    cin >> n;
    stack<double> st;
    for (int i = 0; i < n; ++i) {
        double x; cin >> x;
        st.push(x);
    }

    cout << "Size of the stack: " << st.size() << '\n';
    while (!st.empty()) {
        cout << st.top() << " ";
        st.pop();
    }
    return 0;
}
```

## Output:
<img width="878" height="447" alt="image" src="https://github.com/user-attachments/assets/3c080bfb-35fe-4f1a-806c-6d102dfc7285" />

## Result:
```
Input:
5
10.1 20.2 30.3 40.4 50.5

Output:
Size of the stack: 5
50.5 40.4 30.3 20.2 10.1
```
