It is a JS function that takes another function as an argument and if applied on an array, it will perform the callback function on each element of that array.

official definition: JavaScript `map()` method iterates over an array, applying a callback function to each element, and returns a new array with the results. `The map() method` does not change the original array, and does not execute the function for empty elements.

Example code: 

```
const arr = [1, 2, 3]; // Original Array

function callback(value) {
return value * 2;
}

const arr2 = arr.map(callback);
}

for first iter:
callback(1)

```



