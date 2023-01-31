## 用指针访问结构体
```Cpp
#include<iostream>
using namespace std;

struct Student {
	int age;
	string name;
	int gender;
};

int main() {
	Student s1 = { 20, "Shiwen", 1 };
	Student* p = &s1;
	cout << "The age of s1 = " << p->age << endl;

	system("Pause");
};
```

## 结构体案例1
![1675163331676](https://user-images.githubusercontent.com/95163456/215744279-b92d4b27-c9d8-4ef8-b1be-ce1beedc2188.jpg)
```Cpp
#include<iostream>
using namespace std;

struct Student
{
	string name;
	int grade;
};
struct Teacher
{
	string name;
	Student sArray[5];
};

void allocateSpace(Teacher tArray[], int len) {
	string tName = "Teacher_";
	string sName = "Student_";
	string NameSeed = "ABCDE";
	for (int i = 0; i < 3; i++) {
		tArray[i].name = tName + NameSeed[i];

		for (int j = 0; j < 5; j++) {
			tArray[i].sArray[j].name = sName + NameSeed[j];
			tArray[i].sArray[j].grade = rand() % 100 + 40;
		}
	}
}

void printAll(Teacher tArray[], int len) {
	for (int i = 0; i < 3; i++) {
		cout << tArray[i].name << endl;

		for (int j = 0; j < 5; j++) {
			cout << tArray[i].sArray[j].name << ": " << tArray[i].sArray[j].grade << endl;
		}
	}
}

int main() {
	Teacher tArray[3];
	allocateSpace(tArray, 3);
	printAll(tArray, 3);

	system("pause");
}
```
```
Output:
TeacherA
        Name:StudentA Grade:81
        Name:StudentB Grade:85
        Name:StudentC Grade:91
        Name:StudentD Grade:66
        Name:StudentE Grade:55
TeacherB
        Name:StudentA Grade:87
        Name:StudentB Grade:50
        Name:StudentC Grade:57
        Name:StudentD Grade:40
        Name:StudentE Grade:43
TeacherC
        Name:StudentA Grade:72
        Name:StudentB Grade:64
        Name:StudentC Grade:80
        Name:StudentD Grade:92
        Name:StudentE Grade:58
```

## 案例2
![image](https://user-images.githubusercontent.com/95163456/215753142-f650c7e4-a93b-420c-a7e8-bc5f6c7c7096.png)
```Cpp
#include<iostream>
using namespace std;

struct hero
{
	string name;
	int age;
	string gender;
};

void BubbleSort(hero arr[], int len) {
	for (int i = 0; i < len; i++) {
		for (int j = 0; j < len - i - 1; j++) {
			if (arr[j].age > arr[j + 1].age) {
				hero temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}
}

void printAll(hero arr[], int len) {
	for (int i = 0; i < len; i++) {
		cout << arr[i].name << arr[i].age << endl;
	}
}

int main() {
	struct hero arr[5] =
	{
		{"Liu",23,"M"},
		{"Guan",22,"M"},
		{"Zhang",20,"M"},
		{"Zhao",21,"M"},
		{"Diao",19,"F"},
	};
	BubbleSort(arr, 5);
	printAll(arr, 5);

	system("pause");
}
```
```
Diao19
Zhang20
Zhao21
Guan22
Liu23
```
