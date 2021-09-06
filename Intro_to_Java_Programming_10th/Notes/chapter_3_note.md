# Notes for Chapter 3  
  
## 3.6
### Note 3.6.N1 Dangling Else Ambiguity
```java
int x=3, y=2;

if (x > 2)
			if (y > 2)
			System.out.println("z is " + (x+y));
			else
			System.out.println("x is " + x);
```
The program above outputs:
```
x is 3
```
Clearly, the "else" statement matches the second "if" statement (if(y>2)).  
Called *"dangling else ambiguity"*, the else clause always matches the **most recent unmatched if clause** in the same block.
