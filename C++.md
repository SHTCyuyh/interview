# 0421 快手笔试
## `vector` 和 `list`相关：
Vector：
* vector的数据总是存放在堆上， 对象根据定义（有时候栈，有时候堆）
* 向量（vector）中间的插入和删除是非常昂贵的，因为它需要大量的时间来移动所有的元素
* vector支持随机访问
* push_back()时间复杂度 O(1)

List：
* List更适合顺序访问且适合插入删除；
* 支持双向，并为插入和删除操作提供了一种有效的方法。
* List是连续的容器

## inline
* 关键字inline 必须与函数定义体放在一起才能使函数成为内联，仅将inline 放在函数声明前面不起任何作用 `用于实现的关键字`
* 使用inline修饰避免了频繁调用函数对栈内存重复开辟所带来的消耗。
* inline只适合涵数体内代码简单的函数数使用，不能包含复杂的结构控制语句例如while、switch，并且内联函数本身不能是直接递归函数(自己内部还调用自己的函数)。

## static(静态成员变量)
```
class Student{
public:
    Student(char *name, int age, float score);
    void show();
public:
    static int m_total;  //静态成员变量
private:
    char *m_name;
    int m_age;
    float m_score;
};
```
静态成员变量 m_total
* static 成员变量属于类，不属于某个具体的对象，即使创建多个对象，也只为 m_total 分配一份内存，所有对象使用的都是这份内存中的数据。当某个对象修改了 m_total，也会影响到其他对象。
* static 成员变量必须在类声明的外部初始化:静态成员变量在初始化时不能再加 static，但必须要有数据类型。
        ```
        int Student::m_total = 0;
        ```
* static 成员变量不占用对象的内存，而是在所有对象之外开辟内存，即使不创建对象也可以访问，static 成员变量和普通的 static 变量类似，都在内存分区中的全局数据区分配内存
* static 成员变量既可以通过对象来访问， 也可以通过类来访问
* 