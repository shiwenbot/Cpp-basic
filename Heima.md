## 变量
在这一块内存中我储存了一个值，如果想访问，需要输入地址，比较麻烦。变量存在的意义就是帮助我们管理内存，这样就不需要记住地址编号了

![image](https://user-images.githubusercontent.com/95163456/215540315-53f3ac28-e0bd-4828-beab-6dd8a8d380b5.png)

Syntax of definging a variable:
```Cpp
int variable = 10;
```
## 常量
常量是指程序中不可更改的数据，如果更改了可能会失去实际意义，例如一周有7天

How to define a constant in cpp:
```Cpp
#include <iostream>

//两种方式：
//1.define 宏常量
#define Day 7//Tell cpp to replace all day with 7;
using namespace std;

int main() {

	cout << "There are " << Day << " days in a week." << endl;

	//2.const
	const int month = 12;
	month = 24// This is invalid

	system("Pause");
};
```
