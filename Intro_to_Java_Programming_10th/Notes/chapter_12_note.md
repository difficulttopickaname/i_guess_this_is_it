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
