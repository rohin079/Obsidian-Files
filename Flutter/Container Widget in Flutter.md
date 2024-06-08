## What are Containers? 

![[Pasted image 20231227204610.png]]

```
@override

State<MyHomePage> createState() => _MyHomePageState();

}

  

class _MyHomePageState extends State<MyHomePage> {

@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

title: Text(widget.title),

),

body: Center(

child: Container(

width: 100,

height: 100,

color: Colors.blueAccent,

child: Center(child: Text('Hello container' , style: TextStyle(color: Colors.white),),)

),

)

// This trailing comma makes auto-formatting nicer for build methods.

);

}

}
```

- Containers are used to put childs inside it in which we can put elements.
  
 - We can wrap any widget inside any widget called the **Center** widget which has a child and will put the child inside the center of the screen
   
   Use onlick funtions: [[Inkwell Widget]]
