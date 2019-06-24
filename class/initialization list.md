# initialization list

+ 成员是按照他们在类中出现的顺序进行初始化的，而不是按照他们在初始化列表出现的顺序初始化的。

```c++
#include <iostream>
#include <stdio.h>
using namespace std;

class A{
public:
    int a ;
    A(int t) { cout << "class A constructor" << endl; a = t;}

};

class B{
public:
     int b;
     B (int t){cout << "class B constructor" << endl; b = t;}
};

class C : public A{
public:
    int c;
    B bb;
    C(int t) : bb(1),A(1){cout << "class C constructor" << endl; c = t;}
};

int main(){
    C c(1);
};


```