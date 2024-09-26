
```Dart
enum AnimalType { cat, dog, rabbit }

void test(AnimalType animalType) {
	switch(animalType){
		case AnimalType.cat: print('Miao'); break;
		case AnimalType.dog: print('Bau'); break;
		case AnimalType.rabbit: print('Any sound emitted'); break;
		default: print('no animal providet');
	}
}

void main() {
	test(AnimalType.cat);
}
```
