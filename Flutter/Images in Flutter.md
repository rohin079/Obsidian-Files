
1. Create an `assets` folder in the root directory
   
2. comment out the assets code in `pubspec.yaml` and put the images path as `assets/images/` to include all the images
   
3. Put image using the following code -
	
	![[Pasted image 20231228224520.png]]
```
@override

Widget build(BuildContext context) {

return Scaffold(

appBar: AppBar(

title: Text(widget.title),

),

body: Image.asset('assets/images/test.jpg')

  

// This trailing comma makes auto-formatting nicer for build methods.

);

}

}
```