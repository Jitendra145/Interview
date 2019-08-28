1. What is Memory Leak? Give an example.
Ans. If an application creates lots of objects and does not use them then Garbage Collector can't destroy those objects. As These objects have 
valid reference. Such type of useless objects are called **Memory Leak**.

**Note:** If allocated memory goes beyond limit then program will terminated with **OutOfMemoryError**
```
import java.util.*;
import java.lang.*;
import java.io.*;
 
/* Name of the class has to be "Main" only if the class is public. */
class Ideone
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		Vector v = new Vector(214444); 
        Vector v1 = new Vector(214744444); 
        Vector v2 = new Vector(214444); 
        System.out.println("Memory Leaks");
	}
}
```
**OutPut:Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
	at java.base/java.util.Vector.<init>(Vector.java:142)
	at java.base/java.util.Vector.<init>(Vector.java:155)
	at Ideone.main(Main.java:14)**

https://www.geeksforgeeks.org/internal-working-of-hashmap-java/
https://www.geeksforgeeks.org/java-memory-management/
