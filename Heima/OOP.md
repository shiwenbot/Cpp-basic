## 潜拷贝与深拷贝
```Cpp
#include<iostream>
using namespace std;

class Person {
public:
	Person() {
		cout << "no-argument constructor" << endl;
		m_age = 0;
		m_height = 0;
	}
	Person(int age, int height) {
		cout << "constructor with agrument" << endl;
		m_age = age;
		m_height = new int(height);//放到堆区
	}

	//declared with a reference parameter instead of an object parameter to avoid the creation of a temporary copy of the object
	//深拷贝
	Person(const Person& p) {
		cout << "copy constructor" << endl;
		m_age = p.m_age;
		m_height = new int(*p.m_height);//new就代表从新申请一块内存
	}


	~Person() {
		cout << "dectructor" << endl;
		if (m_height != NULL) {
			delete m_height;
			m_height = NULL;
		}

	}
public:
	int m_age;
	int* m_height;
};

void test01() {
	Person p1(18, 180);
	Person p2 = p1;
	cout << "P1 age = " << p1.m_age << " height = " << *p1.m_height << endl;
	cout << "P2 age = " << p2.m_age << " height = " << *p2.m_height << endl;
}

int main() {

	test01();

	system("pause");
}
```
![image](https://user-images.githubusercontent.com/95163456/216470022-227d687e-f352-4941-b06e-c81191e6344e.png)
由上图可知，浅拷贝会导致堆区的内存重复释放，如果属性有在堆区开辟的，一定要自己提供拷贝构造函数，防止浅拷贝带来的问题
