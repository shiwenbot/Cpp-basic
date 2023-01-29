## pointer
```Cpp
#include<iostream>

using namespace std;

void LOG(int x) 
{
  cout << x << endl;
}

int main()
{
  int var = 9;
  void* ptr = &var; //add & before a variable we will get the memory address of this variable
  *ptr = 10; //dereferencing, change the value at address ptr to 10
  cin.get();
}
```
This is an alternative approach
```Cpp
int main()
{
  char* buffer = new char[8]; //allocate 8 bits of memory and return a pointer at the beginning of that memory
  memset(buffer, 10, 8); // fill in 10 to the blocks, start from the pointer for 8 blocks
}
```
## reference
```Cpp
int a = 5;
int& ref = a; //alias of a, any changes on ref is the same on a
```
Reference is not a variable, every time declare a reference, I have to assign it to a variable

The normal way to increase the value
```Cpp
void Increment(int value) {
  value++;
}

int main()
{
  int a = 5;
  Increment(a);
}
```
Using pointer
```Cpp
void Increment(int* value) {
  (*value)++;
}

int main()
{
  int a = 5;
  Increment(&a); //alias of a, any changes on ref is the same on a
}
```

Using Reference
```Cpp
void Increment(int& value) {
  value++;
}

int main()
{
  int a = 5;
  Increment(a); 
}
```
