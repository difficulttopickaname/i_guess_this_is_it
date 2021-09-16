# Chapter 6
## 6.3
### Note 6.3.N1 Calling a Method
```java
public static void main(String[] args)
```
From the left to the right, "**public**" and "**static**" are modifiers, the return value type is void (which means no return value; in c++, the return value is often 0 in "int main()"), and "**String\[]**" indicates that the parameter is an array of String.   
  
The statements in **main** may invoke other methods that are defined in the class that contains the main method or in other classes.  

### Note 6.3.N2 Call Stack  
Each time a method is invoked, the system creates an **activation record** (also called an activation frame) that stores parameters and variables for the method and places the activation record in an area of memory known as a **call stack**.  
  
(Call stack is also called "execution stack", "runtime stack", "machine stack", or shortened as "the stack".)  
  
When a method calls another method, the caller’s activation record is kept intact, and a new activation record is created for the new method called. When a method finishes its work and returns to its caller, its activation record is removed from the call stack.  
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c6_3_call_stack.png)  
As shown above, call stacks store the activation records in a *last-in, first-out* fashion.
  
## 6.8
### Note 6.8.N3 Overloading Methods
If I have three methods as shown below:
```java
public static int max(int a, int b){
...
}

public static double max(double a, double b){
...
}

public static double max(double a, double b, double c){
...
}
```
Java would automatically determine which method to use when calling "max" method. For example: 
```java
m1 = max(1,2);
m2 = max(1.1, 1.2);
m3 = max(1.1, 1.2, 1.3);
```
"m1", "m2", "m3" calls three different methods. The Java compiler finds the method that best matches a method invocation.
