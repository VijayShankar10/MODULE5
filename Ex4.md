# Ex.No:4  
# Ex.Name: Queue ADT using STL – size, first, and last elements (max size 100)  

## Date:  

## Aim:  
To insert elements into a Queue ADT using STL and display the size, first element, and last element.  

## Algorithm:  
1. Start the program.  
2. Read the number of elements `n`.  
3. Insert the elements into a queue (maximum size 100).  
4. Display:  
   - Size of queue  
   - First element  
   - Last element  
5. Stop the program.  

## Program:
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n; 
    cin >> n;
    queue<int> q;
    for (int i = 0; i < n; i++) {
        int val; cin >> val;
        if (q.size() < 100) q.push(val);
    }

    cout << "Size of the Queue is:" << q.size() << "\n";
    if (!q.empty()) {
        cout << "The First Element of the Queue is:" << q.front() << "\n";
        cout << "The Last Element of the Queue is:" << q.back() << "\n";
    }
}
```

## Output:
<img width="857" height="506" alt="image" src="https://github.com/user-attachments/assets/905d6ebb-1186-49cc-8586-ab9d65ac4810" />

## Result:
```
Input:
7
9 7 6 5 4 3 2

Output:
Size of the Queue is:7
The First Element of the Queue is:9
The Last Element of the Queue is:2
```
