It is used to make sure that if you compare an object with another (of the same type) it can compare it.

```Dart
class Cat extends Object{  
  final String name;  
  
  Cat(this.name);  
  
  @override  
  bool operator ==(covariant Cat other) => other.name == name;  
  
  @override  
  int get hasCode => name.hashCode;  
}
```


Compare in main tow different objects of the same type
```Dart
void main() {
	final cat1 = Cat('Foo');
	final cat2 = Cat('Foo');

	if (cat1 == cat2) print('Same');
	else print('different');
}
```
