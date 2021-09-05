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
		double radius=input.nextDouble(); //reading a double type value as the input
		
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
