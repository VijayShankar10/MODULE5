# Ex.No:5  
# Ex.Name: Write a CPP Program to insert fractional values in to Queue ADT  and display size of the queue,and first,Last element of the queue (use STL and set maximum size of the is 100)  

## Date:  

## Aim:  
To write Last element of the queue using STL.

## Algorithm:  
1. Start the program.  
2. Reverse the infix expression and swap parentheses.  
3. Convert the modified infix to postfix using stack:  
   - Push operators into stack based on precedence and associativity.  
   - Pop when needed to build postfix.  
4. Reverse the postfix to obtain prefix.  
5. Display the prefix expression.  
6. Stop the program.  

## Program:
```cpp
#include <iostream>
#include<queue>
using namespace std;
int main()
{
    queue<float>s;
    int i,n;
    float x[100];
    cin>>n;
    for(i=1;i<=n;i++)
    {
    cin>>x[i];
    s.push(x[i]);
    }
    cout<<"Size of the Queue is:"<<s.size()<<endl;
    cout<<"The First Element of the Queue is:"<<s.front()<<endl;
    cout<<"The Last Element of the Queue is:"<<s.back()<<endl;
    
}
```

## Output:
<img width="1280" height="517" alt="image" src="https://github.com/user-attachments/assets/8661c30d-8d1e-4bcc-9097-2891b90c5f93" />


## Result:
```
Input:
5
65.6 67.4 56.89 76.7 .9
Output:
Prefix expression: -+a*bcd
Input:
A*B+C/D
Output:
Size of the Queue is:5
The First Element of the Queue is:65.6
The Last Element of the Queue is:0.9
```
