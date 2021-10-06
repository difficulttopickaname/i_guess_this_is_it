# Chapter 9
## 9.6
### Note 9.6.N1 Point2D Class
The Point2D class is in **javafx.geometry** package. The following is its UML diagram.  
```java
+Point2D(x: double, y: double)  //Constructs a Point2D object with the specified x- and y-coordinates.

+distance(x: double, y: double): double //Returns the distance between this point and the specified point (x, y).

+distance(p: Point2D): double //Returns the distance between this point and the specified point p.

+getX(): double //Returns the x-coordinate from this point.

+getY(): double //Returns the y-coordinate from this point.

+toString(): String //Returns a string representation for the point.
```

## 9.7
### Note 9.7.N2 Static method
The *radius* variable of a *Circle* object is an instance variable.  
An instance variable is tied to a specific instance of the class; it is not shared among objects of the same class.  
```java
class Circle{
	double radius;
  ...
}
```
  
To let all the instances of a class to share data, use static variables, also known as class variables.  
```java
class Circle{
  static int numberOfObjects;
  ...
}
```
  
### Note 9.7.N3 Instance and Static Method
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c9_8_instance_static.png)
For example, the following is wrong.
```java
int i = 5;
public static void main(String[] args) {
	int j = i; // Wrong because i is an instance variable
}
```
The static method can't access an instance data field.


## 9.8
### Note 9.8.N4 Visible Modifiers  
C1 and C2 are in the same package, while C3 in another one.
![](https://github.com/difficulttopickaname/i_guess_this_is_it/blob/java_beginner/Intro_to_Java_Programming_10th/Pictures/jl_c9_8_visible_modifiers.png)
Note that if a "class" is not defined as "public", it can be accessed only within the same package.  
**Causion**:  
1. The private modifier applies only to the members of a class. The public modifier can apply to a class or members of a class.  
2. Using the modifiers public and private on local variables would cause a compile error.

## 9.12
### Note 9.12.N5 Immutable Objects and Classes
**For a class to be immutable, the following rules must be met:**  
■ *All data fields must be private.*  
■ *There can’t be any mutator methods for data fields.*  
■ *No accessor methods can return a reference to a data field that is mutable.*  
  
A counter example of rule 3:
```java
public java.util.Date getDateCreated() {
	return dateCreated;
}
```
It is clear that the accessor method "getDateCreated" returns a reference to "Date" object, therefore the content of "dateCreated" can be changed.  
  
  
## 9.14
### Note 9.14.N6 "this"
The **"this"** keyword is the name of a reference that an object can use to refer to itself.  
```java
class Circle{
	private double radius = 1;
	...
	double getArea() {
		return Math.PI * this.radius * this.radius;
	}
}
```
Furthermore, the keyword "this" can be applied to constructors.  
```java
class Circle{
	private double radius;
	
	Circle(){
		this(1.0);
	}
	
	Circle(double newRadius){
		radius = (newRadius >= 0) ? newRadius : 0;
	}
	...
}
```
Note: Java requires that the "this(arg-list)" statement appear **first** in the constructor before any other executable statements.  
