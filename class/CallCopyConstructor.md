# 调用拷贝构造函数的情况

```c++

class point{
public:
    point(int xx = 0, int yy = 0){x = xx; y = yy;}
    point(point &p){x = p.x, y = p.y;}; // 不写的话， 编译器会自动生成一个拷贝构造函数，不过是对数据的浅拷贝，在类中存在指针时，最好重新定义一个构造函数
    int getX(){return x;}
    int getY(){return y;}
private:
    int x,y;
};

```

+ 当用类的一个对象去初始化该类的另一个对象

```c++

int main(){
    point a(1,1);
    point b(a);
    cout << b.getX() << " " << b.getY() << endl;
}

```

+ 如果函数的参数是类的对象，调用函数时，进行形参和实参的结合时

```c++

void fX(point p){
    cout << p.getX() << endl;
}

int main(){
    point a(1,1);
    point b(a);
    fX(a);
}

```


+ 如果函数的返回值是类的对象，函数执行完返回调用者时

```C++

point g(){
    point a(1,1);
    return a;
}

int main(){
    point b;
    b = g();
    cout << b.getX() << " " << b.getY() << endl;
    return 0;
}

```
