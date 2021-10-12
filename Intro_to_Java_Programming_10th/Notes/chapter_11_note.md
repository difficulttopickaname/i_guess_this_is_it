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

## 11.8
### Note 11.7.N4 Method Matcing & Dynamic Binding
In an expression "Person p = new Student();", "Person" is the **declared type** of p, while "Student" is the **actual type** of p.  
```java
public class match_and_bind {
	public static void main(String[] args) throws Exception {
        Person p = new Student();
        Student s = new Student();
        
        p.m(0);     // Prints "Person method"
        p.m(0.0);   // Prints "Person method"
        
        s.m(0);     // Prints "Student method"
        s.m(0.0);   // Prints "Person method"
        
        System.out.println(p.toString());	// Prints "Student"
        System.out.println(s.toString());	// Prints "Student"
    }
}


class Person {
    public void m(double n) {
        System.out.println("Person method");
    }
    
    public String toString() {
    	return "Person";
    }
}

class Student extends Person {
    public void m(int n) {
        System.out.println("Student method");
    }
    
    public String toString() {
    	return "Student";
    }
}
```
The "m" methods tests the way JVM matches methods, while the "toString" methods tests how it binds methods.  
  
■ The **declared type** of the reference variable decides which method to **match** at compiletime. It goes backwards the inheritance chain.  
■ The JVM dynamically **binds** the implementation of the method at runtime, decided by the **actual type** of the variable.  
  
## 11.9
### Note 11.9.N5 Explicit Casting and "instanceof"
It is always possible to cast an instance of a subclass to a variable of a superclass (known as upcasting), because an instance of a subclass is always an instance of its superclass.  
```java
Object o = new Student();
```
When casting an instance of a superclass to a variable of its subclass (known as downcasting), explicitcasting must be used to confirm your intention to the compiler with the (SubclassName) cast notation.  
```java
Student b = (Student) o;
```
  
To make sure that "o" (the superclass) is an instance of "Student" (the subclass), use "**instanceof**" operator.
```java
if(p instanceof Student) {
        Student l = (Student)p;
}
```
