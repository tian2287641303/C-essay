# const
const是常量限定符，const对象必须初始化，对象一旦创建其值就不能再发生更改了，默认状态下const只在创建时的当前文件中生效，使const定义的对象在程序中对生效，在多个文件中共享，可以在其它使用到该对象的文件中声明对象。
## 顶层const和底层const
通俗的来说顶层const就是对象本身是const对象，这一点任何对象都可以设置为顶层const。而底层const则只针对于复合类型来说了，底层const就是其所绑定或指向的对象是const对象。指针既可以是顶层const也可以是底层const，而引用则只可以是底层const，因为引用本身不是对象，所以也就不可能是一个常量了。
## const的引用
把引用绑定到const对象上
```
const int a = 5;
const int& b = a;
```
const引用可以绑定到一个非const对象，但不可以通过const引用修改其绑定的非const对象值。
## 指向常量的指针
指向常量的指针不能修改其所指向对象的值，即使它指向的不是一个const对象，要想存放const对象的地址必须使用指向常量的指针。
```
const int a = 5;
const int* b = &a;
```
## 常量指针
常量本身就是一个指针，常量指针指向的对象初始化后不能发生改变。常量指针也可以指向常量，叫做指向常量的常量指针
```
const int a = 1;
int b = 2;
int* const c = &b;
const int* const d = &a;
```

## 常量表达式
常量表达式是指值不会发生改变，并且在编译阶段就可以得到计算结果。用常量表达式初始化的const对象也是常量表达式。
```
const int a = 20+10;
```
### constexpr变量
costexpr声明的变量由编译器来验证变量的值是否是一个常量表达式
```
constexpr int a = 20+10;
```

constexpt只能声明字面值类型为常量表达式