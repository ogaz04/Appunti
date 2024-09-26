The data type in dart is the absence of a value in a variable. In dart you have to specify if it can contain a null value.

You can not use the null value in this case:
```Dart
void main() {
	String name = 'Foo';
}
```

In this case with the <font color="#c00000">question mark</font> you can use <font color="#ffc000">null</font>
```Dart
void main() {
	String? name = null;
}
```

### Data structures (Maps, Lists, Sets...)

If you put the question mark at the end it means that the list it self can be null.
```Dart
void main() {
	List<String>? names = null;
}
```

In this case the variables  can be null.
```Dart
void main() {
	List<String?> names = ['Alessandro', null, 'Michele'];
}
```

If you use the question mark in both places it means that you can do both.
```Dart
void main() {
	List<String?>? names = ['Alessandro', null, 'Michele'];
	names = null;
}
```


### Cherry-picking non-null values

You use it to find the fist non null value
```Dart
void test(String? data1, String? data2, String? data3) {
	final firstNonNullValue = data1 ?? data2 ?? data3;
	print(fristNonNullValue);
}

void main() {
	test(null, 'Alessandro', null);
}
```

Example:
1.  if you provide to the function this type of data: `test(null, 'Alessandro', null);` the output will be `Alessandro`
2. if the data is: `test('Alessandro', null, 'Michele');` then the output will be `Alessandro`. Because it is the first data that does not contain a null value.
3. if all the options are null then the output will be `null`

### Null-aware assignment operator

You use it to assign an other value if the data you provide is null
```Dart
void test(String? data1, String? data2, String? data3) {
	String? name = data1;
	name ??= data2;
	print(name);
}

void main() {
	test(null, 'Alessandro', null);
}
```

in this case you will get the string `Alessandro`. If there was a 'real' data in the first argument then there wouldn't be any change.

### Conditional invocation

If you provide a data structure that can be nullable than you have to use the <font color="#ffc000">question_mark-dot-operation</font> to make sure that you don't get any <font color="#c00000">errors</font>.
Like for the length operation the method searches for data in the list, but if there is any you get an error. If you use the <font color="#c00000">?.</font> to invoke the method then it will provide a null result if the list is empty
```Dart
void test(List<String>? names) {
	final numberOfNames = names?.length;
	print(numberOfNames);
}

void main() {
	List<String>? names = null;
	test(names);
}
```

there is a better method to use this  technique

You use to put 0 in length if the result of `names?.length` is null
```Dart
void test(List<String>? names) {
	final length = names?.length ?? 0;
	print(length);
}

void main() {
	List<String>? names = null;
	test(names);
}
```

