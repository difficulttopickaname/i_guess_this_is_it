# Chapter 17
## 17.4
### Note 17.4.N1 FileInputStream and FileOutputStream
Normally, instances of "FIleInputStream" and "FileOutputStream" are created (and used) as following.  
```java
FileOutputStream output = new FileOutputStream("listing_17_1.dat");
for (int i = 1; i <= 10; i++)
		output.write(i);
output.close();
		
FileInputStream input = new FileInputStream("listing_17_1.dat");
int value;
while((value = input.read()) != -1)
		System.out.print(value + " ");
input.close();
```
  
\*An instance of "FileInputStream" can be used as an argument to construct a Scanner, and an instance of FileOutputStream can be used as an argument to construct a PrintWriter.
```java
new PrintWriter(new FileOutputStream("temp.txt", true));  //"true" make output appended to the original text
```
