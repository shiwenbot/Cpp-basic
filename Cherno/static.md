```Cpp
//int i = 0

void Function()
{
	static int i = 0; //This is equivalent to define i outside the funtion, see above
	i++;
	cout << i << endl;
}

int main()
{
	Function();
	Function();
	Function();
	Function();
}
```

If I define i outside Function(), other people can simple change the value of i in main().
If I use static, I can make sure no one can change it in main()
