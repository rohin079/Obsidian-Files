![[Pasted image 20231228212838.png]]

1. Text Button -
   ![[Pasted image 20231228213619.png]]

2.  Elevated Button - Same functionality but with a realistic #3-D looking button (Recommended)
   
3. Outlined Button

```
@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

title: Text(widget.title),

),

body: TextButton(

child: Text('Hello'),

onPressed: () {

print('Button single pressed');

},

onLongPress: () {

print('Button long pressed');

},

)

  

// This trailing comma makes auto-formatting nicer for build methods.

);

}
```