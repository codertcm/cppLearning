# the order of constructor and destructor 

```C++

#include <iostream>
#include <stdio.h>
using namespace std;

class A{
public:
    A() {cout << "constructor A" << endl;}
    ~A() {cout << "destructor A" << endl;};
};

class C{
public:
    C() {cout << "constructor C " << endl;}
    ~C() {cout << "destructor C " << endl; };
};

class B : public A{
public:
    A a;
    C c;
    B() {cout << "constructor B " << endl;}
    ~B() {cout << "destructor B " << endl;};
};

class D{
public:
    D() {cout << "constructor D " << endl;}
    ~D() {cout << "destructor D " << endl;};
};

D d;

int main(){
    B b;
    cout << "=====================" << endl;
}

````

![运行结果](https://github.com/codertcm/pictures/blob/master/cb_console_runner_qcx0PS0n05.png)
