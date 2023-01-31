## 指针
指针就是地址
```Cpp
#include<iostream>
using namespace std;
int main() {
	int a = 10;
	//defind a pointer
	int* p = &a;
	cout << "The address of a is :" << &a << endl;
	cout << "p is: " << p << endl;

	//We can use pointer to read and write the value in that address
	*p = 100;
	cout << "The value of a is " << a << " now." << endl;
};
```

```
Output:
The address of a is :000000E4AB53F9F4
p is: 000000E4AB53F9F4
The value of a is 100 now.
```

## const修饰指针
```Cpp
1. const int * p = &a;
此时指针的指向可以修改，但不可以更改指向的值，即：
p = &b //是合法的
*p = 20 //是不合法的

2.int * const p = &a;
此时指向不可以改，指向的值可以
```

## 用指针访问数组
```Cpp
#include<iostream>
using namespace std;
int main() {
	int arr[8] = { 1,2,3,4,5,6,7,8 };
	cout << "The first value is " << arr[0] << endl;

	int* ptr = arr;
	cout << "Use pointer to access the first value:" << *ptr << endl;
};
```

```
Output:
The first value is 1
Use pointer to access the first value:1
```

## 指针的地址传递
```Cpp
#include<iostream>
using namespace std;

void swap(int *p1, int *p2) {
	int temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}

int main() {
	int a = 10;
	int b = 20;
  
  //在传入地址后，用两个指针*p1, *p2来接收
	swap(&a, &b);
	cout << "a = " << a << endl;
	cout << "b = " << b << endl;
};
```
详细的代码解释可以参考p62


