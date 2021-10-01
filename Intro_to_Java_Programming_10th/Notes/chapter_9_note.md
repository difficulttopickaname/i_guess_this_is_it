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