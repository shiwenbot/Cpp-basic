# 第二章
## Q1 显示姓名和地址
```Cpp
#include <iostream>

int main() {

    using namespace std;

    cout << "Hi there, I'm Shujia Huang from Shenzhen, Guangdong, China" << endl;
    return 0;
}
```

## Q2 用户输入一个以浪为单位的数字，将其转换为码
```Cpp
#include <iostream>

int main() {
	using namespace std;

	cout << "Please enter how many lang: " << endl;
	int lang;
	cin >> lang;
	cout << "That will be " << 220 * lang << "ma." << endl;
	return 0;
}
```

## Q3 编写一个C++程序，它使用 3 个用户定义的函数（包括main()），并生成下面的输出：

```bash

Three blind mice
Three blind mice
See how they run
See how they run

```
其中一个函数要调用两次，该函数生成前两行；另一个函数也被调用两次，并生成其余的输出。

## Q4 编写一个程序，摄氏度变华氏度：

```bash
Please enter a Celsius value: 20
20 Celsius is 68 degrees Fahrenheit.

```
```Cpp
#include <iostream>

using namespace std;

void CtoF(double c) {
	double f = 1.8 * c + 32;
	cout << c << " degrees Celsius is " << f << " degrees Fahrenheit." << endl;
}

int main() {
	double c;
	cout << "Please enter a Celsius value: ";
	cin >> c;
	CtoF(c);

	return 0;
}
```

## Q6 编写一个程序，要求用户输入小时数和分钟数。在 main() 函数中，将这两个值传递给一个void函数，后者以下面这样的格式显示这两个值：

```bash

Enter the number of hours: 9
Enter the number of minutes: 28

Time: 9:28
```
```Cpp
#include <iostream>

using namespace std;

void time(int hour, int minute) {
	cout << "Please enter hour: " << hour << endl;
	cout << "Please enter minute: " << minute << endl;
	cout << "Tiem: " << hour << ":" << minute << endl;
}

int main() {
	int hour, minute;
	cin >> hour;
	cin >> minute;
	time(hour, minute);
}
```
