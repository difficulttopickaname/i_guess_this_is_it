# Notes for Chapter 2  
  
## 2.1  
### Note 2.1.N1 Taking an Input
JAVA DOESN'T DIRECTLY SUPPORT CONSOLE INPUT. So, in order to type input directly, the **Scanner** class is needed to create an object to read input from *System.in*.  
  
First of all, "Scanner" is in the *java.util* package. Import it before using.  
``
import java.util.Scanner;
`` 
  
Create a Scanner type object and assigns it to the variable 'input'.  
``
Scanner input = new Scanner(System.in);
``
  
To read a "double" type value, the "nextDouble()" method is needed.  
``
double a = input.nextDouble();
``
  
The entire program is shown below:  

```java
package chapter_2_learning;

import java.util.Scanner; //importing the Scanner class
//or use "import java.util.*;" as a wildcard import.

public class listing_2_2 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in); //defining "input" for further use
		
		System.out.println("Type in the radius:"); //prompt
		double radius = input.nextDouble(); //reading a double type value as the input
		
		double area = radius*radius*3.14159;
		
		System.out.println("Area for radius " + radius + " = " + area);
	}
}
```
  
## 2.12
### Note 2.12.N2 Current Time
The following code displays how to obtain current time.
```java
package chapter_2_learning;

public class listing_2_7 {
	public static void main(String[] args) {
		long totalMilliseconds = System.currentTimeMillis();
		
		long totalSeconds = totalMilliseconds / 1000;
		long currentSecond = totalSeconds % 60;
		
		long totalMinutes = totalSeconds / 60;
		long currentMinute = totalMinutes % 60;
		
		long totalHours = totalMinutes / 60;
		long currentHour = totalHours % 24;
		
		System.out.println("current time is: "+currentHour+":"+currentMinute+":"+currentSecond+" GMT");
		
	}
}

```
In the program, **"System.currentTimeMillis()"** returns the number of milliseconds since the UNIX epoch (Jan. 1st, 1970).  
Output of this program is shown below.
```
current time is: 0:24:48 GMT
```
  
## 2.14
### Note 2.14.N3 Increment and Decrement  
```java
i = 1;
a = i++; //a=1,i=2

i = 1;
b = ++i; //b=2,i=2

i = 1;
c = i--; //c=1,i=0

i = 1;
d = --i; //d=0,i=0
```
  
## 2.15
### Note 2.15.N4 Casting
1. Casting does not change the variable being cast.  
```java
double a = 4.5;
int b = (int) a;
// a = 4.5, b = 4
```
2. An argument assignment expression would cast the result to the assigned variable's type.  
```java
int sum = 0;
sum += 4.5; //this is equivalent to sum = (int)(sum + 4.5)
```

### Note 2.15.N5 Two Digits after Decimal Point
```java
double a = 344.24345;
double b = (int)(a * 100) / 100.0; //b = 344.24
```
Due to the casting operation "(int)" only affects the first number afterwards- in this case, '(a*100)'- the division operation is done later. Therefore, the data type returns to "double."
  
## 2.16
### Error 2.18.E1 Round-off Errors
When trying to find the decimal part of 99.99: 
```java
System.out.print((int)((99.99 - 99) * 100));
```
The syntax above is correct, but it results in the "wrong" output below:  
```
98
```
This is because calculations involving floating-point numbers are **approximated** because these numbers are not stored with complete accuracy.  
### Solution 2.18.S1 Round-off Errors
To yield a precise result, calculations with integers is needed instead, and the program is modified as below.
```java
System.out.print((int)(99.99 * 100 - 99 * 100));
```
Which would result in: 
```
99
```
