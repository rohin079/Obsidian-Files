In Java, whenever you call a function with some argumentin variables ( like number ),

then the copy of those variables are actually based to the function as parameters not the original variables.

example:
  psvm{

int a = 10;
int b = 20;

sum(a, b)
}  

now inside the sum function a copy of values of a and b are passed. this is called call my value.

