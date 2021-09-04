# Notes for Chapter 1  

## 1.8 
### Error 01
When I'm attempting to realize **figure 1.9**, the following error occurs:
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c1_8_error_package_1.png)

The second to the last line indicates that the computer "Could not find or load main class".

According to my [source program](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Source_code/java_1_32.java), 
```java
package world_001;

public class java_1_32 {
	public static void main(String[] args) {
		System.out.println("3.5*4/2-2.5 is ");
		System.out.println(3.5*4/2-2.5);
	}
}
```
obviously, java failed to find the package 'world_001' in the first line of the source code.

### Solution 01
I simply go back to the parent directory, and the program runs smoothly.
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c1_8_error_package%20_2%20.png)
  
  
  
## 1.10
### Note 1.10.N1
```java
public class LogicError {
	public static void main(String[] args) {
		System.out.println(9/5);
		System.out.println(9.0/5);
	}
}
```  
The output of this Program is shown below:  
```
1
1.8
```  
According to "Introduction to Java Programming", "In Java, the division for integers is the quotient- the fractional part is truncated- so '9/5' is 1."  
Therefore, I need to use floats as the quotient to get the correct answer in floats. (Which is quite different from python.)
