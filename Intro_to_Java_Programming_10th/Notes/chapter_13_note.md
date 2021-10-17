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
