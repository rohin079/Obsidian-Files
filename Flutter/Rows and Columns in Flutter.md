
![[Pasted image 20231228225027.png]]

- Multiple child option called children which is like an array given by the `children[]` widget 
  
- Both Rows and Columns have 2 types of alignments: `mainAxisAlignment` and `crossAxisAlignment`
  
- For row the main alignment is horizontally and axis is vertically and vice-versa for column 
  
```
body: const Row(

  

mainAxisAlignment: MainAxisAlignment.spaceAround,

crossAxisAlignment: CrossAxisAlignment.center,

  

children: [

Text('Text 1', style: TextStyle(fontSize: 25)),

Text('Text 2', style: TextStyle(fontSize: 25)),

Text('Text 3', style: TextStyle(fontSize: 25)),

Text('Text 4', style: TextStyle(fontSize: 25)),

Text('Text 5', style: TextStyle(fontSize: 25))

],

)

  

// This trailing comma makes auto-formatting nicer for build methods.

);

}
```

