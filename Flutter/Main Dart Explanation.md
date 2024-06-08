The main file of the application is **_main.dart_** and it is the entry point of the Flutter application. Let’s see what this file contains.

![](https://miro.medium.com/v2/resize:fit:700/1*5bA9u8A46aa-QrpCm3p6qg.png)


## Import statements

The first line of the file is an import statement which is importing a **_material_** package from the Flutter framework.

import 'package:flutter/material.dart';

## Main function

After this line, we see the main function. The main function is the entry point of the file. This is the function from which the execution begins (similar to C/C++ language). The main function calls a method call **_runApp_** which is taking **_MyApp_** as a parameter. The task of this function is to _inflate the given widget and attach it to the screen._ This means the **_MyApp_** widget will be attached to the screen.

void main() {  
    runApp(const MyApp());  
}

## MyApp widget

The **_MyApp_** is a **_stateless_** widget that has a constructor with named parameters taking **_key_** as a parameter. This method overrides the **_build_** method which takes the **_context_** of the type **_BuildContext_** as a parameter and returns a **_Widget_**.  
The **_build_** method returns a **_MaterialApp_** with the title **_“Flutter Demo”.  
_**It also has a named parameter called **_theme_** which takes **_ThemeData_** as a parameter, so the **_ThemeData_** is passed to it by setting the **_primarySwatch_** attribute of **_ThemeData_** to **_blue.  
_**The **_MaterialApp_** also has an attribute called **_home_** and it takes a **_Widget_** as its value. We are passing **_MyHomePage_** to it. It is taking **title** as a named parameter.

class MyApp extends StatelessWidget {  
    const MyApp({Key? key}) : super(key: key);     @override  
    Widget build(BuildContext context) {  
        return MaterialApp(  
            title: 'Flutter Demo',  
                theme: ThemeData(  
                    primarySwatch: Colors.blue,  
                ),            home: const MyHomePage(  
                title: 'Flutter Demo Home Page',  
            ),  
        );  
    }  
}

