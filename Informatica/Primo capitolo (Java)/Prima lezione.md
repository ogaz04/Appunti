
```dart
import 'package:flutter/material.dart';  
  
void main() {  
  runApp(App());  
}  
  
class App extends StatelessWidget {  
  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      home: HomePage(),  
    );  
  }  
}  
  
  
class HomePage extends StatelessWidget {  
  
  @override  
  Widget build(BuildContext context) {  
    return Scaffold(  
      appBar: AppBar(  
        title: Text("Flutter2Starter"),  
        centerTitle: true,  
      ),  
      body: Center(  
        child: Text("Empty"),  
      ),  
      drawer: Drawer(  
        child: ListView(  
          padding: EdgeInsets.all(0),  
          children: [  
            DrawerHeader(  
              decoration: BoxDecoration(  
                image: DecorationImage(  
                  image: NetworkImage("link"),  
                  fit: BoxFit.cover,  
                  colorFilter: ColorFilter.mode(Colors.black38, BlendMode.darken)  
                )              ),  
              child: Padding(  
                padding: const EdgeInsets.only(bottom: 16),  
                child: Column(  
                  crossAxisAlignment: CrossAxisAlignment.start,  
                  mainAxisAlignment: MainAxisAlignment.end,  
                  children: [  
                    Text("@alessandrozago",  
                      style: TextStyle(  
                        color: Colors.white,  
                        fontSize: 16,  
                        fontWeight: FontWeight.bold  
                      ),  
                    ),  
                  ],  
                ),  
              ),  
            ),  
            ListTile(  
              onTap: () {  
                Navigator.pop(context);  
              },  
              leading: Icon(Icons.home),  
              title: Text("Home"),  
            ),  
            ListTile(  
              onTap: () {  
                Navigator.pop(context);  
              },  
              leading: Icon(Icons.person),  
              title: Text("Profilo"),  
            ),  
          ],  
        ),  
      ),  
    );  
  }  
}
```

