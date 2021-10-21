# Chapter 17
## 17.4
### Note 17.4.N1 FileInputStream and FileOutputStream
Normally, instances of "FileInputStream" and "FileOutputStream" are created (and used) as following.  
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
  
### Note 17.4.N2 DataInputStream and DataOutputStream
DataInputStream reads bytes from the stream and converts them into appropriate primitive-type values or strings.  
DataOutputStream converts primitive-type values or strings into bytes and outputs the bytes to the stream.  
```java
DataOutputStream output = new DataOutputStream(new FileOutputStream("listing_17_2.dat"));
output.writeUTF("John");
output.writeDouble(85.5);
output.writeUTF("Jim");
output.writeDouble(185.5);
output.writeUTF("George");
output.writeDouble(105.25);
output.close();
	
DataInputStream input = new DataInputStream(new FileInputStream("listing_17_2.dat"));
System.out.println(input.readUTF() + " " + input.readDouble());
System.out.println(input.readUTF() + " " + input.readDouble());
System.out.println(input.readUTF() + " " + input.readDouble());
input.close();
```
