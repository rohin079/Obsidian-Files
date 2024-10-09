1. 1-D arrays:
   
initialise an array = `int arr[] = new int[5];`
or `int arr[] = {1, 3, 4}` 

Traverse an array ```

```
for (int i=0; i<arr.length; i++){

System.out.println(arr[i]);
}
```

2. 2-D arrays

Declaration `int arr[][]= new int[2][3]`

![[Pasted image 20240101123726.png]]

output :

![[Pasted image 20240101123815.png]]

```
  

import java.util.*;

  

public class Main{

  
  

public static void main(String[] args) {

Scanner sc = new Scanner(System.in);

  

int row = sc.nextInt();

int col = sc.nextInt();

  

int num[][] = new int[row][col];

  

//input

for(int i=0; i<row; i++){

for(int j=0; j<col; j++){

num[i][j] = sc.nextInt();

}

}

//printing mattrix

for(int i=0; i<row; i++){

for(int j=0; j<col; j++){

System.out.print(num[i][j] + " ");

}

System.out.println();

}
}
}
```















