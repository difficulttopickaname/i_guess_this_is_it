# Chapter 7
## 7.2
### Note 7.2.N1 Foreach Loops
Used for traversing the array sequentially without using an index variable.  
```java
String[] myList = {"a","now","b"};
for (String a: myList){
  System.out.println(a);
}
```
The code above would have the following output.
```
a
now
b
```
  
## 7.6
### Note 7.6.N2 Passing Arrays to Methods
There are important differences between passing the values of variables of **primitive data types** and passing **arrays**.  
```java
public class test_7_6 {
	public static void main(String[] args) {
		int x = 1;
		int[] y = new int[]{0};
		
		value_change(x,y); //this method attempts to change the value of both x,y into 100
		System.out.println(x);
		System.out.println(y[0]);
	}
	public static void value_change(int number, int[] array) {
		number = 100;
		array[0] = 100;
	}
}
```
Attempting to change both x,y in the method, the following is the result.  
```java
1   //x
100 //y
```  
■ For an argument of a primitive type, the argument’s value is passed.  
■ For an argument of an array type, the value of the argument is a reference to an array; this reference value is passed to the method. Semantically, it can be best described as pass-by-sharing, that is, the array in the method is the same as the array being passed. Thus, *if you change the array in the method, you will see the change outside the method.*  
  
Note that elements inside an array are still of primitive type.
