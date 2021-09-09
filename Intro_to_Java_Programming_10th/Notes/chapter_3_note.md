# Notes for Chapter 3  
  
## 3.6
### Note 3.6.N1 Dangling Else Ambiguity
```java
int x=3, y=2;

if (x > 2)
			if (y > 2)
			System.out.println("z is " + (x+y));
			else
			System.out.println("x is " + x);
```
The program above outputs:
```
x is 3
```
Clearly, the "else" statement matches the second "if" statement (if(y>2)).  
Called *"dangling else ambiguity"*, the else clause always matches the **most recent unmatched if clause** in the same block.
  
## Practice
### Note P3.9.N2 Formatting the Output
In order to print the leading 0, an integer has to be cast into String type.  
```java
int isbn = 013601267;
String isbn_str = String.format("%09d", isbn);
System.out.print(isbn_str);
```
In the second line of the program, "0" is added before the parameter with data type "d", to make up the number of digits needed- which is "9".  
The output is as below.
```
013601267
```
Note that if "%-09d" is used instead, "0" will be added AFTER the parameter, which also suggests that the parameter is left justified.
