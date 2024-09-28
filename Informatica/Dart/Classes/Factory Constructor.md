A factory constructor is used to create multiple constructors but with different initializations. Like in Java when you used to have multiple constructors
```Dart
class Cat {  
  final String name;  
  
  //Default constructor
  Cat(this.name);  

  //FluffBall constructor
  factory Cat.fluffBall() {  
    return Cat('Fluff ball');  
  }  

  //NameInUpperCase constructor
  factory Cat.nameInUpperCase(String name) {  
    return Cat(name);  
  }  
}
```


You could invoke the constructor you'd like

```Dart
void main() {
  final cat1 = Cat('Luigi');  
  print(cat1.name);

  final cat2 = Cat.fluffBall();  
  print(cat2.name);

  final cat3 = Cat.nameInUpperCase('Jack');  
  print(cat3.name);
}
```
