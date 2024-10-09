![[Pasted image 20240106023118.png]]

```
class _MyHomePageState extends State<MyHomePage> {

@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

title: Text(widget.title),

),

body: Center(

// ignore: sized_box_for_whitespace

child: Container(

width: 300,

child: const TextField(

decoration: InputDecoration(border: OutlineInputBorder()),

),

))

  

// This trailing comma makes auto-formatting nicer for build methods.

);

}

}
```

![[Pasted image 20240106024528.png]]


![[Pasted image 20240106024907.png]]


![[Pasted image 20240106025222.png]]


