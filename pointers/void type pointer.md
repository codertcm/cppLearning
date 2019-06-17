# void type pointers

## 1. void的作用

+ a. 对函数参数的限定：当不需要传入参数时，即 function (void);
+ b. 对函数返回值的限定：当函数没有返回值时，即 void function(void);

## 2. void指针的作用

+ a. void指针可以指向任意的数据类型，即任意类型的指针可以赋值给void指针int *a;

    ```c++
    void *p;
    p=a;
    ```

    如果void指针赋值给其他类型，则需要强制转换；a=（int *）p;

+ b. 在ANSI C标准中不允许对void指针进行算术运算，因为没有特定的数据类型，即在内存中不知道移动多少个字节；而在GNU标准中，认为void指针和char指针等同。
  
## 3. 应用

+ a.void指针一般用于应用的底层，比如malloc函数的返回类型是void指针，需要再强制转换；
+ b.文件句柄HANDLE也是void指针类型，这也是句柄和指针的区别；
+ c.内存操作函数的原型也需要void指针限定传入参数：

    ```c++
    void * memcpy (void *dest, const void *src, size_t len);
    void * memset (void *buffer, int c, size_t num );
    ```
  
+ d. 面向对象函数中底层对基类的抽象。
  