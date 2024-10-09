#### Basics:

 Strongly typed as compared to loosely typed in case of Javascript
 
 Browsers don't support TS so under the hood we need to compile it to JS and then run the JS file as we normally run.

compile the TS file using `tsc 'file-name'` command.

#### TS Config File:

Initialise the the tsc config file :

>tsc --init

This will create the tsconfig.json file

### Define a function:

This is how we can define a function in typescript:

>function sum(a:number, b:number ) :number{
>	return a+b
>}

Define an arrow function: 

>const sum = (a:number, b:number ) :number => {
>	return a+b
>}

**Type Annotation**: 

In TS, type annotation is a way of explicitly specifying a type of a variable, function parameter or a function return value

![[Pasted image 20240604192742.png]]

 By using `any` datatype we can use TS with loosely type annotations like JS

**Optional and default function parameters**: 

![[Pasted image 20240605011510.png]]

Any parameter can be made optional by adding a `?` after the parameter name.

![[Pasted image 20240605011642.png]]

**Iterating over an array using of for loop**:

![[Pasted image 20240605012640.png]]

**Filter array method**:

![[Pasted image 20240605013728.png]]

### Typescript Type Aliases

Type alias is a way to give a name to a specific type or combination of types just like struct data type in C. It allows you to create a custom name for a type making it easier to reuse.

![[Pasted image 20240605015648.png]]


### Enums :

Enums in TS are commonly used when you want to display a set of related values and choose one value from multiple options. Enums provide a convenient way to define a set of named values and associate them with specific meanings.

![[Pasted image 20240605022126.png]]

![[Pasted image 20240605022141.png]]

### Interface :


![[Pasted image 20240605023156.png]]

### Classes in TS :

We can define classes in TS by - 

>class Persons {
>name : string;
>age : number;
>hobbies : string[]
>
>constructor(name:string, age:number, hobbies: string[]){
>this.name: name;
>this.age: age;
>this.hobbies: hobbies; 
>}
>}

for a class to inherit this class we can simply use `extends` keyword, the same how we used to do in Java.

>class students `extends` persons {}

While inheriting a class, the constructor defined in the parent class must also be used and to use the properties of the parent class inside the child constructor a `super(name: name, age: age)` keyword used like this.

make an instance of a class by:

>const person1 = new Persons(name: "rohin", age: 20, hobbies: ["reading", "writing"]);

**Access modifiers in TS**:

![[Pasted image 20240605120404.png]]

**Static keyword in TS**:

`Static` keyword in TS allows you to directly access methods and properties of a class without creating any instance of the class.

ex:  

>class mathOperations{
>public static add(num1: number, num2: number): number{
>	return num1 + num2
>	}
>}
>
>//directly accessing w/o creating class instance
>console.log(mathOperations.add(1, 4));  


![[Pasted image 20240617022943.png]]

![[Pasted image 20240617113354.png]]