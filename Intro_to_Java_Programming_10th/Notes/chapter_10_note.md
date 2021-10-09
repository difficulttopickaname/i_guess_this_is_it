# Chapter 10
## 10.11
### Note 10.11.N1 StringBuffer Class
The "**StringBuffer**" and "**StringBuilder**" class are similar to the "String" class except that the String class is immutable.  
  
The following shows methods aiming for *modification* in the StringBuilder class.  
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c10_11_stringbuilder_modifying_class.png)  
  
And the following shows methods aiming for *manipulation* in the StringBuilder class.  
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c10_11_stringbuilder_manipulating_class.png)  
  
### Error 10.11.E1 StringBuffer.equals()
```java
String original = "abcd*@dcba%";
StringBuilder clear = clearString(original); //the method returns a clear stringbuilder with only numbers and characters
StringBuilder reverse = reverseString(clear); //the method returns a reversed stringbuilder
System.out.println(clear.equals(reverse));
```
The output is shown below.  
```java
false
```
Although the "clear" and "reverse" looks the same, they are not "equal".

### Solution 10.11.S1 StringBuffer.equals()
Although the "equals()" method in "String" class check whether two Strings look the same, the "equals()" method in "StringBuilder" class checks whether two StringBuilders has the *same reference* (as what "==" in String class do).  
  
Therefore, an easy way is to convert the final StringBuilder into String.  
```java
String original = "abcd*@dcba%";
StringBuilder clear = clearString(original); //the method returns a clear stringbuilder with only numbers and characters
StringBuilder reverse = reverseString(clear); //the method returns a reversed stringbuilder
System.out.println(clear.toString().equals(reverse.toString()));
```
And here's the result.
```java
true
```
