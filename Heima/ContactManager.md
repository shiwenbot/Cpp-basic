```Cpp
#include<iostream>
using namespace std;

void showMenu() {
	cout << "***************************" << endl;
	cout << "*****  1.add" << endl;
	cout << "*****  2.show"   << endl;
	cout << "*****  3.delete  " << endl;
	cout << "*****  0.exit  " << endl;
	cout << "***************************" << endl;
}

struct Person {
	string name;
	int m_sex;
	int m_age;
	string m_number;
};

#define MAX 1000
struct AddressBook{
	struct Person pArray[MAX];
	int m_size;
};

void addPerson(AddressBook *ab) {
	if (ab->m_size == MAX) {
		cout << "Address Book is full." << endl;
		return;
	}
	else {
		//name
		string name;
		cout << "Please enter the name: ";
		cin >> name;
		ab->pArray[ab->m_size].name = name;

		//sex
		int sex;
		cout << "Please enter sex, 0 for Male and 1 for Female: ";
		while (true) {
			cin >> sex;
			if (sex == 1 || sex == 0) {
				ab->pArray[ab->m_size].m_sex = sex;
				break;
			}
			cout << "Please enter a valid sex." << endl;
		}

		//age
		int age;
		cout << "Please enter the age";
		cin >> age;
		ab->pArray[ab->m_size].m_age = age;

		//number
		string number;
		cout << "Please enter the phone number: ";
		cin >> number;
		ab->pArray[ab->m_size].m_number = number;

		//update size
		ab->m_size++;
		cout << "Add successful!" << endl;

		cout << ab->pArray[ab->m_size].name;
	}
}

void showPerson(AddressBook *ab) {
	if (ab->m_size == 0) {
		cout << "There is no contact in the app now." << endl;
		return;
	}
	else {
		for (int i = 0; i < ab->m_size; i++) {
			cout << "Name: " << ab->pArray[i].name << endl;
			cout << "Sex: " << (ab->pArray[i].m_sex == 0 ? "Male" : "Female") << endl;
			cout << "Number: " << ab->pArray[i].m_number << endl;
		}
	}
	
	system("pause");
}

int isExist(AddressBook* ab, string name) {
	for (int i = 0; i < ab->m_size; i++) {
		if (ab->pArray[i].name == name) {
			return i;
		}
	}
	return -1;
}

void deletePerson(AddressBook* ab) {
	cout << "Please tell me the contact you want to delete";
	string name;
	cin >> name;

	int a = isExist(ab, name);
	if (a != -1) {
		for (int i = a; i < ab->m_size; i++) {
			ab->pArray[i] = ab->pArray[i + 1];
		}
		ab->m_size--;
		cout << "Delete successfull!" << endl;
	}
	else {
		cout << "Cannot find this person." << endl;
	}

	system("pause");
	system("cls");
}

int main() {

	int select;
	AddressBook ab;
	ab.m_size = 0;

	//主逻辑
	while (true) {
		showMenu();

		cin >> select;

		switch (select) {
		case 1:
			addPerson(&ab);
			break;
		case 2:
			showPerson(&ab);
			break;
		case 3:
			deletePerson(&ab);
			break;
		case 0:
			cout << "Thanks for using our system! See you next time!" << endl;
			system("pause");
			return 0;
			break;
		}

	}

	system("pause");
}
```
