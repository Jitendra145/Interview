# Interview
This repository contains all the question I faced during an interview
## important link
### Spring Auto-Wiring Beans with @Autowired annotation
https://www.mkyong.com/spring/spring-auto-wiring-beans-with-autowired-annotation/
### in-java-can-we-pass-superclass-object-to-subclass-reference
https://stackoverflow.com/questions/24384547/in-java-can-we-pass-superclass-object-to-subclass-reference
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
