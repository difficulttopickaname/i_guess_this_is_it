# Chapter 6
## 6.3
### Note 6.3.N1 Calling a Method
```java
public static void main(String[] args)
```
From the left to the right, "**public**" and "**static**" are modifiers, the return value type is void (which means no return value; in c++, the return value is often 0 in "int main()"), and "**String\[]**" indicates that the parameter is an array of String.   
The statements in **main** may invoke other methods that are defined in the class that contains the main method or in other classes.  

### Note 6.3.N2 Call Stack  
Each time a method is invoked, the system creates an activation record (also called an activation frame) that stores parameters and variables for the method and places the activation record in an area of memory known as a call stack.  
Call stack is also called "execution stack", "runtime stack", "machine stack", or shortened as "the stack".  
When a method calls another method, the caller’s activation record is kept intact, and a new activation record is created for the new method called. When a method finishes its work and returns to its caller, its activation record is removed from the call stack.  
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c6_3_call_stack.png)  
As shown above, call stacks store the activation records in a last-in, first-out fashion.
