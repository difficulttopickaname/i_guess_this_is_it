# Notes for Chapter 2  
  
## 2.1  
### Taking an Input
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
``
package chapter_2_learning;

import java.util.Scanner; \\importing the Scanner class
\\or use "import java.util.*;" as a wildcard import.

public class listing_2_2 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in); \\defining "input" for further use
		
		System.out.println("Type in the radius:"); \\prompt
		double radius=input.nextDouble(); \\reading a double type value as the input
		
		double area = radius*radius*3.14159;
		
		System.out.println("Area for radius " + radius + " = " + area);
	}
}
``
