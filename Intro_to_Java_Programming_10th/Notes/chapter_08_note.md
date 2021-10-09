# Chapter 8
## 8.3
### Note 8.3.N1 Initializing two-dimensional arrays
A two dimensional array "list\[]\[]" has "list.length" rows and "list\[i].length" columns on the ith row.  
```java
for (int row = 0; row < matrix.length; row++) {
	for (int column = 0; column < matrix[row].length; column++) {
		matrix[row][column] = input.nextInt();
	}
}
```
Above is a way to initialize a two dimensional array with input values.
