1. Sort the object based on its property using Java 8?

**Ans:**

https://www.mkyong.com/java8/java-8-how-to-sort-list-with-stream-sorted/

```
class Ideone
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		LinkedList<Integer> ls = new LinkedList<>();
		ls.add(1);
		ls.add(2);
		ls.add(3);
		List<Integer> ls1 = ls.stream().sorted(Comparator.reverseOrder()).collect(Collectors.toList());
		ls1.forEach(System.out::println);
	}
}
```

```
/* package whatever; // don't place package name! */

import java.util.*;
import java.lang.*;
import java.io.*;
import java.util.stream.*;

/* Name of the class has to be "Main" only if the class is public. */
class User{
	String name;
	User(String name){
		this.name = name;
	}
	public String getName(){
		return name;
	}
	
	public String toString(){
		return "User Name: "+name;
	}
}
class Ideone
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		LinkedList<User> ls = new LinkedList<>();
		ls.add(new User("jitendra"));
		ls.add(new User("Cathy"));
		ls.add(new User("Amit"));
		List<User> ls1 = ls.stream().sorted(Comparator.comparing(User::getName))
									.collect(Collectors.toList());
		ls1.forEach(System.out::println);
	}
}
####Output:###
Success #stdin #stdout 0.1s 36672KB
User Name: Amit
User Name: Cathy
User Name: jitendra
```
2. Remove elements from LinkedList using java8?

**Ans:**

1. using Collection.removeIf()
```
class Ideone
{
	public static void main (String[] args) throws java.lang.Exception
	{
		// your code goes here
		LinkedList<Integer> ls = new LinkedList<>();
		ls.add(1);
		ls.add(2);
		ls.add(3);
		ls.removeIf(i->i%2==0);
		//Stream<Integer> st = ls.stream();
		//List<Integer> ls1 = st.filter(i->i%2!=0).collect(Collectors.toList());
		for(Integer i : ls){
			System.out.println(i);
		}
	}
}
```
2. Removing Elements with Stream
```
  Stream<Integer> st = ls.stream();
	List<Integer> ls1 = st.filter(i->i%2!=0).collect(Collectors.toList())
```
3. Collectors.partitioningBy

https://www.baeldung.com/java-collection-remove-elements

https://www.baeldung.com/java-use-remove-item-stream

3. Fibonnaci series with Java 8 approach?

**ANS:**

https://www.mkyong.com/java/java-fibonacci-examples/?utm_source=mkyong.com&utm_medium=Referral&utm_campaign=afterpost-related&utm_content=link4


4. Caching in spring?
5. @PathParam vs @QueryParam vs @FormParam
6. @Component,@Configuration etc
7. Jdbc vs Hibernate Query?
8. Different type of object creation?
9. Dialect in Hibernate
10. implementing all the abstract methods of interface is necesary?

**Ans:**

The only way around this is to declare your class as abstract and leave it to a subclass to implement the missing methods. But ultimately, someone in the chain has to implement it to meet the interface contract. If you truly do not need a particular method, you can implement it and then either return or throw some variety of NotImplementedException, whichever is more appropriate in your case.

The Interface could also specify some methods as 'default' and provide the corresponding method implementation within the Interface definition (https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html). These 'default' methods need not be mentioned while implementing the Interface.

https://stackoverflow.com/questions/11437097/not-implementing-all-of-the-methods-of-interface-is-it-possible

11. SpringBoot annotation?

https://www.java67.com/2018/06/top-15-spring-boot-interview-questions-answers-java-jee-programmers.html

**ANS:**

Some of the most common Spring Boot annotations are @EnableAutoConfiguration, @SpringBootApplication, @SpringBootConfiguration, and @SpringBootTest.

The @EnableAutoConfiguration is used to enable auto-configuration on Spring Boot application, while @SpringBootApplication is used on the Main class to allow it to run a JAR file. @SpringBootTest is used to run unit test on Spring Boot environment.

12. Volatile keyword
13. Ways to create thread?
14. Use of making a class Final?

**Ans:** 
The keyword final itself means something is final and is not supposed to be modified in any way. If a class if marked final then it can not be extended or sub-classed. But the question is why do we mark a class final? IMO there are various reasons:

**Standardization:** Some classes perform standard functions and they are not meant to be modified e.g. classes performing various functions related to string manipulations or mathematical functions etc.

**Security reasons:** Sometimes we write classes which perform various authentication and password related functions and we do not want them to be altered by anyone else.

15. Security feature used in your app?
16. how start internally call run method?
17. classes used in java.util package?

https://www.wisdomjobs.com/e-university/java-8-interview-questions.html

http://javabypatel.blogspot.com/2018/06/java-8-stream-practice-problems.html

https://www.baeldung.com/spring-order

https://dzone.com/articles/how-to-use-cookies-in-spring-boot


