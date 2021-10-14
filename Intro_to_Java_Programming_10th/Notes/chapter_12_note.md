# Chapter 12
## Note 12.2.N1 Exception Handling
```java
public static int quotient(int number1, int number2) {
	if (number2 == 0)
		throw new ArithmeticException("Divisor cannot be zero");
		
	return number1 / number2;
}
		
public static void main(String[] args) {
	try {
	...
	}
	catch (ArithmeticException ex) {
		System.out.println("Exception: an integer cannot be divided by zero ");
	}
		
	System.out.println("Execution continues ...");  // Note that this will still be executed after the "try" or "catch" block
}
```
It basically forms a try-throw-catch block where exceptions are dealt with more elegantly.  
  
Loop until the user enters a correct input.
```java
do {
	try {
		int number1 = input.nextInt();
		int number2 = input.nextInt();
		...
	}
	catch (ArithmeticException ex) {
		System.out.println("Exception: an integer " +"cannot be divided by zero ");
		input.nextLine();	//discards the current input line so that the user can enter a new line of input
	}
}
while(!endinput);
```
  
## 12.7
### Note 12.7.N2
Every method must state the types of checked exceptions it might throw. This is known as *declaring exceptions*.  
**Error** and **RuntimeException** (unchecked exceptions) are not required to be declared explicitly in the method.  
  
To declare an exception in a method, use the throws keyword in the method header, as in this example:
```java
public void method1() throws IOException
```
  
Note that if a method contains another method that might throw an exception, the first method also need to declare the exception.
  
## 12.11
### Note 12.11.N3 PrintWriter and Scanner
Use **PrintWriter** to write data into a file.
```java
package chapter_12_learning;

import java.io.IOException;

public class listing_12_13 {
	public static void main(String args[]) throws IOException {  // the PrintWriter might throw IOException, so it's declared here.
		java.io.File filename = new java.io.File("D:\\Mine\\Application\\Eclipse\\work\\hello_world\\src\\chapter_12_learning\\file\\test_output.txt");
		if(filename.exists()) {
			System.out.println("File already exists! ");
			System.exit(0);
		}
		
		java.io.PrintWriter output = new java.io.PrintWriter(filename);
		
		output.print("U I, Uv gone away.");
		output.println("2018");
		
		output.close();
	}
}
```
Use **Scanner** to read data from file.
```java
package chapter_12_learning;

public class listing_12_15 {
	public static void main(String[] args) throws Exception{  // the Scanner might throw Exception, so it's declared here.
		java.io.File filename = new java.io.File("D:\\Mine\\Application\\Eclipse\\work\\hello_world\\src\\chapter_12_learning\\file\\test_output.txt");
		
		java.util.Scanner input = new java.util.Scanner(filename);
		
		int linenum = 0;
		while(input.hasNext()) {
			linenum++;
			String line = input.nextLine();
			System.out.printf("line %d: %s\n",linenum,line);
		}
		
		input.close();
	}
}
```
  
#### About how the Scanner class works
The next(), nextLine()... methods are known as token-reading methods, because they read tokens separated by delimiters.  
\* A token-reading method first *skips any delimiters* (whitespace characters by default), then *reads a token ending at a delimiter*.
\* The next() method reads a string delimited by delimiters, and nextLine() reads a line ending with a line separator.

```java
Scanner input = new Scanner(System.in);
int intValue = input.nextInt();
String line = input.nextLine();
```
Suppose I enter 34, press the *Enter key*, then enter 567 and press the *Enter key*, the value for "intValue" would be 34 and the value for "line" would be empty.

*Reason: The nextLine() method ends after reading the line separator and returns the string read before the line separator. Since there are no characters before the line separator, line is empty.*
