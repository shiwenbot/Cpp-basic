## 数据类型
存在意义：为变量分配合适的内存空间

![image](https://user-images.githubusercontent.com/95163456/215547678-71e4de3f-ca73-4a32-99c7-43728648691a.png)
![image](https://user-images.githubusercontent.com/95163456/215549806-91bcd719-a741-4bdd-b386-0594c5789fd9.png)


取值范围：1 byte = 8 bits，以short为例，第一位存储符号，剩余的15位都可以存储数字，每个bit有两种可能性0或者1，因此范围就是2^15。
sizeof
```Cpp
#include <iostream>

using namespace std;
//use sizeof to remain us the size of memory for different data type
int main() {
	int variable = 10;
	cout << "The size of int is " << sizeof(variable) << endl;
	system("Pause");
};
```
```Cpp
Output: 4
```

## 函数的值传递
```Cpp
//test pass by value
#include <iostream>

using namespace std;

void swap(int a, int b) {
	cout << "Before swap: a = " << a << " b = " << b << endl;

	int temp = a;
	a = b;
	b = temp;

	cout << "After swap: a = " << a << " b = " << b << endl;
}

int main() {
	int a = 10, b = 15;
	swap(a, b);
	cout << "Test pass by value in main: a = " << a << " b = " << b << endl;
};
```

## 函数的分文件编写
使用头文件<.h>帮助我们
```
1.创建一个新的cpp文件，定义所需函数
2.创建.h文件，声明这个函数
3.在main的文件开头写上预处理语句#include "Header.h"
注意，iostream用了<>，这里我们用了""，表示这个是自创的头文件
```
