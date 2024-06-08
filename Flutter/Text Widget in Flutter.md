
![[Pasted image 20231228210536.png]]

```
@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

title: Text(widget.title),

),

body: const Text('Hello', style: TextStyle(

color: Colors.greenAccent,

fontStyle: FontStyle.italic,

fontWeight: FontWeight.w400,

fontSize: 34

),)

// This trailing comma makes auto-formatting nicer for build methods.

);

}

}
```

