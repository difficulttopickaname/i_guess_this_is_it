# Chapter 11
## 11.2
### Note 11.2.N1 Inheritance Notification
  
■ A subclass is not a subset of its superclass. In fact, a subclass usually contains more information and methods than its superclass.  
  
■ Private data fields in a superclass are not accessible outside the class. They can be accessed/mutated through public accessors/mutators if defined in the superclass.
  
■ Not all is-a relationships should be modeled using inheritance.  
  
■ Inheritance is used to model the is-a relationship. A subclass and its superclass must have the is-a relationship.  
  
■ Java does not allow multiple inheritance. A Java class may inherit directly from only one superclass. This restriction is known as single inheritance. (multiple inheritance can be achieved through interfaces)  
  
## 11.5
### Note 11.5.N2 Overloading and Overriding
\*Overloading means to define multiple methods with the same name but **different signatures**.  
\*Overriding means to provide a **new implementation** for a method in the subclass.
  
■ Overridden methods are in different classes related by inheritance; overloaded methods can be either in the same class or different classes related by inheritance.  
  
■ Overridden methods have the same signature and return type; overloaded methods have the same name but a different parameter list.  
  
Use the notation "@Override" before the method in a subclass to avoid mistakes.  
```java
public class CircleFromSimpleGeometricObject extends SimpleGeometricObject {
  ...
  
	@Override
	public String toString() {
		return super.toString() + "\nradius is " + radius;
	}
  ...
}
```
If a method with the "@Override" annotation does not override its superclass’s method, the compiler will report an error.
  
## 11.7
### Note 11.7.N3 Polymorphism
In simple term, polymorphism means that a variable of a supertype can refer to a subtype object.  
```java
public static void main(String[] args) {
	display(new RectangleFromSimpleGeometricObject(1, 1, "black", true));
}

public static void display(SimpleGeometricObject object) {
	System.out.println("Created on " + object.getDateCreated() + ". Color is " + object.getColor());
}
```
Note that the "display" method takes in a "SimpleGeometricObject" type, where its **subclass** "RectangleFromSimpleGeometricObject" can also be used.  
  
*The three pillars of object-oriented programming are encapsulation, inheritance, and polymorphism.*

