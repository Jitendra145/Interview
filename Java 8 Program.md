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
