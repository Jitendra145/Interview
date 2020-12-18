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

### https://www.objectdb.com/java/jpa/persistence/managed

README.md
collection of java-interview-questions
These resources are not mine, it is just a collection of java-interview-questions I found on the internet. Handy for referring before going for an interview. Multi threading can be ignored by beginners and mid level developers

Table of Contents
No.	Questions
Core Java Interview Questions – Part 1
1	Super Collection of 224 Java Questions ?
2	Is Java Pass by Reference or Pass by Value ?
3	What is the use of the finally block? Is finally block in Java guaranteed to be called? When finally block is NOT called?
4	Why there are two Date classes; one in java.util package and another in java.sql?
5	What is Marker interface?
6	Why main() in java is declared as public static void main?
7	What is the difference between creating String as new() and literal?
8	How does substring() inside String works?
9	What is polymorphism in java, OOPS?
10	What is abstraction in java, OOPS?
11	Can you compare Encapsulation vs Abstraction, OOPS?
12	Difference between Interface vs. Abstract Class ?
13	What is Enum, Explain in detail?
14	What is Java main() method
15	Why Strings are Immutable in Java?
16	How to create immutable class in Java ?
17	What are Java Best Practices ?
18	COllection of Java Puzzle interview questions ?
19	What are SOLID Principles ?
20	What is Open closed principle ?
21	What is Single responsibility principle ?
22	What is Java Singleton Pattern ?
23	What is Java Factory Pattern ?
24	What is Abstract Factory Pattern ?
25	What is Java8 Static & Default methods ?
26	Collection of Java8 Interview Questions and Answers ?
27	Collection of Multi-threading Questions and Answers ?
28	Collection of JavaCollection Interview Questions and Answers ?
29	Collection of Hibernate Interview Questions and Answers ?
30	Collection of JDBC Interview Questions ?
31	Collection of Java Programs ?
32	Collection of Servlets Interview Questions and Answers ?
33	Collection of Java Multiple Choice Questions ?
34	What is everything you know about Java Synchronized Blocks ?
35	What is Java Volatile Keyword ?
36	How to create a immutable object in Java? Count all benefits?
37	What is difference between interfaces and abstract classes?
38	When do you override hashCode and equals()?
Core Java Interview Questions – Part 2
39	Why finalize() method should be avoided?
40	Why HashMap should not be used in multithreaded environment? Can it cause infinite loop as well?
41	Explain abstraction and encapsulation? How are they related?
42	Difference between interfaces and abstract classes?
43	How StringBuffer save the memory?
44	Why wait and notify is declared in Object class instead of Thread ?
45	Write Java program to create deadlock in Java and fix it ?
46	What happens if your Serializable class contains a member which is not serializable? How do you fix it?
47	Explain transient and volatile keywords in java?
48	Difference between Iterator and ListIterator?
Core Java Interview Questions – Part 3
49	Everything about object cloning ?
50	Java hashCode() and equals() – Contract, rules and best practices ?
51	Java Memory Management – Garbage Collection Algorithms
52	Java Serialization – Dos and Don’ts ?
53	Collection of All String Java Questions ?
54	Create object without ‘new’ keyword ?
55	Java Wrapper Classes Internal Caching ?
Collection Interview questions
56	What is the Java Collections API? List down its advantages?
57	Explain Collections hierarchy?
58	Why Collection interface does not extend Cloneable and Serializable interface?
59	Why Map interface does not extend Collection interface?
60	Why we use List interface? What are main classes implementing List interface?
61	How to convert an array of String to ArrayList?
62	How to reverse the list?
63	Why we use Set interface? What are main classes implementing Set interface?
64	How HashSet store elements?
65	Can a null element added to a TreeSet or HashSet?
66	Why we use Map interface? What are main classes implementing Map interface?
67	What are IdentityHashMap and WeakHashMap?
68	Explain ConcurrentHashMap? How it works?
69	How hashmap works?
70	How to design a good key for hashmap?
71	What are different Collection views provided by Map interface?
72	When to use HashMap or TreeMap?
73	How does HashMap works
74	Eight questions on HashMap and ConcurrentHashMap Interview Questions
75	Difference between Set and List?
76	Difference between List and Map?
77	Difference between HashMap and HashTable?
78	Difference between Vector and ArrayList?
79	Difference between Iterator and Enumeration?
80	Difference between HashMap and HashSet?
81	Difference between Iterator and ListIterator?
82	Difference between TreeSet and SortedSet?
83	Difference between ArrayList and LinkedList?
84	Java ConcurrentHashMap Best Practices
85	How to make a collection read only?
86	How to make a collection thread safe?
87	Why there is not method like Iterator.add() to add elements to the collection?
88	What are different ways to iterate over a list?
89	What do you understand by iterator fail-fast property?
90	What is difference between fail-fast and fail-safe?
91	How to avoid ConcurrentModificationException while iterating a collection?
92	What is UnsupportedOperationException?
93	Which collection classes provide random access of it’s elements?
94	What is BlockingQueue?
95	What is Queue and Stack, list their differences?
96	What is Comparable and Comparator interface?
97	What are Collections and Arrays class?
Multi Threading Interview Questions
98	Java DelayQueue
99	ExecutorService – shutdown(), shutdownNow() and awaitTermination​()
100	ExecutorService – Cancel a task in executor
101	ScheduledExecutorService – Running task in executor after delay
102	ExecutorService invokeAll()
103	ExecutorService invokeAny()
104	Callable Future Example
105	Executor RejectedExecutionHandler
106	ExecutorService in Java
107	A Guide to AtomicInteger in Java
108	Producer Consumer Problem Using BlockingQueue
109	Java Thread Life Cycle and Thread States
110	Concurrency vs. Parallelism
111	Java Multi-threading Evolution and Topics
112	Difference between lock and monitor – Java Concurrency
113	ScheduledThreadPoolExecutor – Task Scheduling with Executors
114	Java Callable Future Example
115	Java Fixed Size Thread Pool Executor Example
116	Java Thread Pool – ThreadPoolExecutor Example
117	ConcurrentLinkedDeque Example – Non-blocking Thread-safe List
118	Control concurrent access to multiple copies of a resource using Semaphore
119	How to work with wait(), notify() and notifyAll() in Java?
120	Binary Semaphore Tutorial and Example
121	How to Use Locks in Java java.util.concurrent.locks.Lock Tutorial and Example
122	Creating Threads Using java.util.concurrent.ThreadFactory
123	Java ThreadLocal Variables – When and How to Use?
124	Restarting threads using UncaughtExceptionHandler
125	Java Compare and Swap Example – CAS Algorithm
126	Java Concurrency – Difference between yield() and join()
127	Java Concurrency – Thread Safety?
128	Throttling Task Submission Rate with ThreadPoolExecutor and Semaphore
129	Java concurrency – CountDownLatch Example
130	Java executor framework tutorial and best practices
131	Difference between Runnable vs Thread in Java
132	Difference between sleep() and wait() in Java
133	Object level lock vs Class level lock in Java
134	Java Inter-thread Communication – PipedReader and PipedWriter
135	Java ThreadPoolExecutor and BlockingQueue Example
136	Java Deadlock Example and Solution
