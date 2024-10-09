
1. Bubble sort : Sort the biggest element to last
   
   In Bubble Sort algorithm, 

- traverse from left and compare adjacent elements and the higher one is placed at right side. 
- In this way, the largest element is moved to the rightmost end at first. 
- This process is then continued to find the second largest and place it and so on until the data is sorted.

![[Pasted image 20240101170304.png]]

```
  

import java.util.*;

  

public class Main {

  

public static void printArray(int arr[]) {

for (int i = 0; i < arr.length; i++) {

System.out.print(arr[i] + " ");

}

  

}

  

public static void main(String[] args) {

  

int arr[] = { 7, 8, 12, 6 };

  

for (int i = 0; i < arr.length - 1; i++) {

for (int j = 0; j < arr.length - i - 1; j++) {

if (arr[j] > arr[j + 1]) {

// swap

  

int temp = arr[j];

arr[j] = arr[j + 1];

arr[j + 1] = temp;

}

}

  

}

  

printArray(arr);

  

}

}
```

2. Selection Sort

**Selection sort** is a simple and efficient sorting algorithm that works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and moving it to the sorted portion of the list.