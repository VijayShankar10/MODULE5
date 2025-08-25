# Ex.No:5  
# Ex.Name: Infix to Prefix Conversion using Stack (STL)  

## Date:  

## Aim:  
To convert an infix expression into a prefix expression using Stack STL.  

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
#include <bits/stdc++.h>
using namespace std;

int prec(char c) {
    if (c=='^') return 3;
    if (c=='*'||c=='/') return 2;
    if (c=='+'||c=='-') return 1;
    return 0;
}
bool rightAssoc(char c){ return c=='^'; }
bool isOp(char c){ return c=='+'||c=='-'||c=='*'||c=='/'||c=='^'; }

string infixToPrefix(string s){
    reverse(s.begin(), s.end());
    for(char &c : s){
        if(c=='(') c=')';
        else if(c==')') c='(';
    }

    stack<char> st;
    string postfix;
    for(char c : s){
        if(isalnum(c)) postfix+=c;
        else if(c=='(') st.push(c);
        else if(c==')'){
            while(!st.empty() && st.top()!='('){ postfix+=st.top(); st.pop(); }
            st.pop();
        }
        else if(isOp(c)){
            while(!st.empty() && (prec(st.top())>prec(c) || 
                 (prec(st.top())==prec(c) && !rightAssoc(c)))){
                postfix+=st.top(); st.pop();
            }
            st.push(c);
        }
    }
    while(!st.empty()){ postfix+=st.top(); st.pop(); }
    reverse(postfix.begin(), postfix.end());
    return postfix;
}

int main(){
    string infix; cin >> infix;
    cout << "Prefix expression: " << infixToPrefix(infix) << "\n";
}
```
## Output:
```
Input:
a+b*c-d
Output:
Prefix expression: -+a*bcd
Input:
A*B+C/D
Output:
Prefix expression: +*AB/CD
```
## Result:
<img width="870" height="411" alt="image" src="https://github.com/user-attachments/assets/073c40d2-3cef-476c-a379-53df39ea78ed" />

