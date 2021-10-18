# Chapter 13
## 13.2
### Note 13.2.N1 Abstract Class
```java
public abstract class GeometricObjects{
	...
	public abstract double getArea();  //will be rewriten in subclass
	
	public abstract double getPerimeter();  //will be rewriten in subclass
}

public class Circle extends GeometricObjects{
	...
}

public class Rectangle extends GeometricObjects{
	...
}
```
As above, the "GeometricObjects" is an abstract class containing methods include two abstract methods.  
  
Therefore, the following can be tested.  
```java
public static void main(String[] args) {
	GeometricObjects geoObject1 = new Circle(5);
	GeometricObjects geoObject2 = new Rectangle(5, 3);
	
	System.out.print(equalArea(geoObject1,geoObject2));
}

public static boolean equalArea(GeometricObjects obj_1, GeometricObjects obj_2) {
	return obj_1.getArea() == obj_2.getArea();
}
```
The JVM dynamically determines which of these methods to invoke at runtime, depending on the actual object that invokes the method.  
Note that without defining **abstract methods** in the superclass "GeometricObjects", such comparison cannot be realized.  
  
  
#### Points about Abstract Class  
■ An abstract method cannot be contained in a nonabstract class.  
  If a subclass of an abstract superclass does not implement all the abstract methods, the subclass must be defined as abstract.  
  
■ An abstract class cannot be instantiated using the new operator, but you can still define its constructors, which are invoked in the constructors of its subclasses.  
  For instance, the constructors of GeometricObject are invoked in the Circle class and the Rectangle class.  
  
■ A class that contains abstract methods must be abstract.  
  However, it is possible to define an abstract class that doesn’t contain any abstract methods. In this case, you cannot create instances of the class using the new operator. This class is used as a base class for defining subclasses.  
  
■ A subclass can override a method from its superclass to define it as abstract.  
  This is very unusual, but it is useful when the implementation of the method in the superclass becomes invalid in the subclass. In this case, the subclass must be defined as abstract.  
  
■ A subclass can be abstract even if its superclass is concrete.  
For example, the "Object" class is concrete, but its subclasses, such as "GeometricObject", may be abstract.  
  
■ You cannot create an instance from an abstract class using the new operator, but an abstract class can be used as a data type.  
  Therefore, the following statement, which creates an array whose elements are of the GeometricObject type, is correct.  
``
GeometricObject[] objects = new GeometricObject[10];
``  
You can then create an instance of GeometricObject and assign its reference to the array like this:  
``
objects[0] = new Circle();
``  
  
## 13.4
### Note 13.4.N2 GregorianCalendar and Calendar
#### Field Constants in the Calendar Class
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c13_4_calendar.png)  
  
#### About the two classes
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c13_4_gregorian_calendar.png)  

#### Defining a GregorianCalendar
```java
import java.util.*;

public class listing_13_6 {
	public static void main(String[] args) {
		Calendar calendar = new GregorianCalendar();
		System.out.println("Current time is " + new Date());
		System.out.println("YEAR: " + calendar.get(Calendar.YEAR));
		System.out.println("AM_PM: " + calendar.get(Calendar.AM_PM));
		
		Calendar calendar1 = new GregorianCalendar(2002, 12, 31);
		String[] dayNameOfWeek = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
		System.out.println("December 31, 2002 is a " + dayNameOfWeek[calendar1.get(Calendar.DAY_OF_WEEK) - 1]);
	}
}
```
Note that "Calendar" cannot be used to directly create an instance, therefore the "CregorianCalendar" subclass is needed. The following is the output.  
```java
Current time is Sun Oct 17 11:29:30 CST 2021
YEAR: 2021
AM_PM: 0
December 31, 2002 is a Friday
```
  
## 13.5
### Note 13.5.N3 Interface
An interface is a class-like construct that contains only constants and abstract methods.
```java
public interface Edible {
	public abstract String howToEat();
}
```
Above, an interface "Edible" is created. To specify a class with it, use the keyword "**implements**".
```java
abstract class Fruit implements Edible{
	@Override
	public abstract String howToEat();
}

class Apple extends Fruit implements Edible{
	...
	@Override
	public String howToEat() {
		return "peal and eat";
	}
}
```
