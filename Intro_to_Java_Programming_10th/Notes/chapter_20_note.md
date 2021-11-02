# Chapter 20
## 20.4
### Note 20.4.N1 Comparable and Comparator
#### Comparable
Comparable is a "sorting" interface. In order to "implements" it, the "**compareTo(E o)**" method must be realized.  
```java
public class GeometricObjectCompare implements Comparable<GeometricObject> {
  
	public int compareTo(GeometricObject o) {
		...
	}
  
}
```
As above, it's now capable to use "Arrays.sort" method to sort geometric objects.
  
#### Comparator
Comparator is a "comparing" interface. In order to "implements" it, the "**Compare(E o1, E o2)**" method must be realized, while "equals(Object obj)" is not necessarily needed.  
```java
public class GeometricObjectComparator implements Comparator<GeometricObject>{
	
  public int compare(GeometricObject o1, GeometricObject o2) {
		...
	}
  
}
```
This would realize the following code:  
```java
public static GeometricObject max(GeometricObject g1, GeometricObject g2, Comparator<GeometricObject> c) {
	if (c.compare(g1, g2) > 0)
		return g1;
	else
		return g2;
	}
}
```
