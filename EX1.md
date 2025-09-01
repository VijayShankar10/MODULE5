# Ex.No:1  
# Ex.Name: Add two numbers using multilevel inheritance (protected base members)  

## Date:  

## Aim:  
To write a C++ program that declares two input variables as `protected` in a base class, reads the first value in a first derived class, reads the second value in a further-derived class, and performs the addition in that most-derived class.  

## Algorithm:  
1. Start the program.  
2. Define a base class `Numbers` with `protected` members `a` and `b`.  
3. Define a derived class `FirstInput` to read the first value.  
4. Define another derived class `SecondInputAndSum` to read the second value and perform addition.  
5. In the main function:  
   - Create an object of `SecondInputAndSum`.  
   - Call the functions to read both numbers.  
   - Call the function to calculate and display the sum.  
6. Stop the program.  

## Program:
```cpp
#include <iostream>
using namespace std;

class Numbers {
protected:
    long long a, b;
};

class FirstInput : public Numbers {
public:
    void readFirst() { cin >> a; }
};

class SecondInputAndSum : public FirstInput {
public:
    void readSecond() { cin >> b; }
    void printSum() { cout << "The Result is:" << (a + b) << '\n'; }
};

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    SecondInputAndSum obj;
    obj.readFirst();
    obj.readSecond();
    obj.printSum();
    return 0;
}
```

## Output:
<img width="862" height="361" alt="image" src="https://github.com/user-attachments/assets/dd587035-f9b1-43c4-8396-95f4683fe4ee" />

## Result:
```
Input:
10 20
Output:
The Result is:30
```
