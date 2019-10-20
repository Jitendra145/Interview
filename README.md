# Interview
This repository contains all the question I faced during an interview

http://www.javainterview.in/p/java-serialization-interview-questions.html

## important link
### Spring Auto-Wiring Beans with @Autowired annotation
https://www.mkyong.com/spring/spring-auto-wiring-beans-with-autowired-annotation/
### in-java-can-we-pass-superclass-object-to-subclass-reference
https://stackoverflow.com/questions/24384547/in-java-can-we-pass-superclass-object-to-subclass-reference
### Java Output Questions
https://www.geeksforgeeks.org/output-java-programs-set-12/
### how-to-count-the-number-of-occurrences-of-an-element-in-a-list in Java 8
https://stackoverflow.com/questions/505928/how-to-count-the-number-of-occurrences-of-an-element-in-a-list
```
/* package whatever; // don't place package name! */

import java.util.*;
import java.lang.*;
import java.io.*;
import java.util.stream.Collectors;
/* Name of the class has to be "Main" only if the class is public. */
class Ideone
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		//List<String> list = new ArrayList<>();
		ArrayList<String> animals = new ArrayList<String>();
		animals.add("bat");
		animals.add("owl");
		animals.add("bat");
		animals.add("bat");
		
		Map<String, Long> counts =
    	animals.stream().collect(Collectors.groupingBy(e -> e, Collectors.counting()));
    	for(Map.Entry map:counts.entrySet()){
    		System.out.println(map.getKey()+"-->"+map.getValue());
    	}
	}
}
```
### Java Stack and Heap: Java Memory Allocation
https://www.guru99.com/java-stack-heap.html

### https://howtodoinjava.com/interview-questions/real-java-interview-questions-asked-for-oracle-enterprise-manager-project/
### https://howtodoinjava.com/interview-questions/java-interview-questions-for-mid-level-developers/
