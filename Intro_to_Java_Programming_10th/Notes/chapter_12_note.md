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
