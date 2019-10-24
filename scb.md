**HashMap Vs. ConcurrentHashMap Vs. SynchronizedMap**
**Ans:**
**HashMap**
1. HashMap is non-Synchronized in nature i.e. HashMap is not Thread-safe whereas ConcurrentHashMap is Thread-safe in nature.
2. HashMap performance is relatively high because it is non-synchronized in nature and any number of threads can perform simultaneously. But ConcurrentHashMap performance is low sometimes because sometimes Threads are required to wait on ConcurrentHashMap.
3. While one thread is Iterating the HashMap object, if other thread try to add/modify the contents of Object then we will get Run-time exception saying ConcurrentModificationException.Whereas In ConcurrentHashMap we wont get any exception while performing any modification at the time of Iteration.

2)You can make HashMap synchronized by wrapping it on Collections.synchornizedMap(HashMap) which will return a collection which is almost equivalent to Hashtable, where every modification operation on Map is locked on Map object while in case of ConcurrentHashMap, thread-safety is achieved by dividing whole Map into different partition based upon Concurrency level and only locking particular portion instead of locking the whole Map.

Difference between ConcurrentHashMap and HashMap in Java Collection3) ConcurrentHashMap is more scalable and performs better than Synchronized HashMap in the multi-threaded environment while in Single threaded environment both HashMap and ConcurrentHashMap gives comparable performance, where HashMap only slightly better.


In Summary Main difference between ConcurrentHashMap and HashMap in Java Collection turns out to be thread-safety, Scalability, and Synchronization. ConcurrentHashMap is a better choice than synchronized HashMap if you are using them as cache, which is the most popular use case of a Map in Java application. ConcurrentHashMap is more scalable and outperforms when a number of reader threads outnumber the number of writer threads.


**ConcurrentHashMap**
1. You should use ConcurrentHashMap when you need very high concurrency in your project.
2. It is thread safe without synchronizing the whole map.
3. Reads can happen very fast while write is done with a lock.
4. There is no locking at the object level.
5. The locking is at a much finer granularity at a hashmap bucket level.
6. ConcurrentHashMap doesn’t throw a ConcurrentModificationException if one thread tries to modify it while another is iterating over it.
7. ConcurrentHashMap uses multitude of locks.

**SynchronizedHashMap**
1. Synchronization at Object level.
2. Every read/write operation needs to acquire lock.
3. Locking the entire collection is a performance overhead.
4. This essentially gives access to only one thread to the entire map & blocks all the other threads.
5. It may cause contention.
6. SynchronizedHashMap returns Iterator, which fails-fast on concurrent modification.

https://crunchify.com/hashmap-vs-concurrenthashmap-vs-synchronizedmap-how-a-hashmap-can-be-synchronized-in-java/


**-hashcode vs equals in java**

**-hashcode rule with jpa**
**Is the default implementation of hashcode()/equals() good enough for most cases?**
https://stackoverflow.com/questions/1638723/how-should-equals-and-hashcode-be-implemented-when-using-jpa-and-hibernate
The answer is yes, in most cases it is.

You only need to override equals() and hashcode() if the entity will be used in a Set (which is very common) AND the entity will be detached from, and subsequently re-attached to, hibernate sessions (which is an uncommon usage of hibernate).

using the JPA entity business key(e.g. a unique combination of attributes that is not going to change during object (or, at least, session) lifetime) for equals and hashCode is always best choice. However, not all entities feature a unique business key, so we need to use another database column that is also unique, as the primary key.

https://vladmihalcea.com/how-to-implement-equals-and-hashcode-using-the-jpa-entity-identifier/

https://stackoverflow.com/questions/39100383/why-to-override-hashcode-and-equals-methods-in-hibernate-persistence-class?noredirect=1&lq=1

**-oracle cluster index vs non-cluster index**
Clustered and Non-clustered index are the types of single-level ordering index where clustered index determines how the data is stored in the rows of a table. On the other hand, the non-clustered index stores the data at a single place and the indexes are stored at another place

Non-clustered index creates a logical order for data rows and uses pointers to physical data files. The clustered index physically sort all data rows. The non-clustered index does not sort rows physically. There can be only one clustered index on the table

There can be only one clustered index per table. However, you can create multiple non-clustered indexes on a single table. Clustered indexes only sort tables. Therefore, they do not consume extra storage. Non-clustered indexes are stored in a separate place from the actual table claiming more storage space

-plsql equals null vs is null (careful here, when interviewer says orally "equals" he means "=")

-complete spring container lifecycle

-scrum: chicken & pig story 

For a client/server software architecture, what are the solutions for good user experience with slow client connection

# Skype Question
1. Explain about your project?
2. Java 8 and its feature?
3. diffrence between java 6 and java 8
4. Singleton class
5. Create singlton class
6. What if two thread acces singleton class

**Ans:**

It can be used in a single threaded environment because multiple threads can break singleton property because they can access get instance method simultaneously and create multiple objects

Using synchronized we can create singleton class in multi-threading environment also but it can cause slow performance, so we can use Double check locking mechanism.

https://www.geeksforgeeks.org/java-singleton-design-pattern-practices-examples/

7. How to create thread
8. What is executor framework?
9. How to define no of thread in executor framework?
10. How to find whether a thread stops and complete its work
11. for which scenario do you have used thread in your application
12. have you worked on oracle?
13. Is column with primary key is indexed by default or have to do it manually?
14. What is decode function in oracle?
15. Difference between procedure and function?
16. have you worked on microservices?
17. how microservices communicates with each other and what did you use for communication?

Microservices use service discovery which acts as a guide to find the route of communication between each of them. Microservices then communicate with each other via a stateless server i.e. either by HTTP Request/Message Bus. These microservices communicate with each other using an Application Program Interface(API)

18. How will you map same URI with multiple method if Spring controller?

@RequestMapping with Request Parameters
The params element of the @RequestMapping annotation further helps to narrow down request mapping. Using the params element, you can have multiple handler methods handling requests to the same URL, but with different parameters.

19. Have you worked on hibernate?
20. What is Docker and Microservices?
21. What is the difference between an API and a Microservice?

Here are the main differences between APIs and microservices: An API is a contract that provides guidance for a consumer to use the underlying service. A microservice is an architectural design that separates portions of a (usually monolithic) application into small, self-containing services.
Microservices are an increasingly popular architecture for building large-scale applications. Rather than using a single, monolithic codebase, applications are broken down into a collection of smaller components called microservices. ... Docker is an excellent tool for managing and deploying microservices

http://higherdevelopers.com/2018/09/01/standard-chartered-interview-questions-and-experience-for-java-developer-profile/

https://stackoverflow.com/questions/34587254/accessing-multiple-controllers-with-same-request-mapping

https://stackoverflow.com/questions/3898442/spring-mvc-mapping-multiple-urls-to-same-controller

https://springframework.guru/spring-requestmapping-annotation/


## Symantec

1. How to return value from Thread?
2. If we having multiple Thread then how will you return value?
3. Have you heard about callable interface?
4. Have you heard about Cloneable interface?
5. Have you used Hash map? Is Hash map Thread safe?
6. How to get thread safe version of HashMap?
7. What is Concurrent Hash map?
8. What is size of concurrent hash map size?
9. Explain hash map internal implementation?
10. How you insert data in hashmap?
11. Have you created custom immutable class?
12. Have you created singleton pattern?
13. How will you implement singleton class?
14. What is the different between SOAP and REST?
15. How will you implement versioning in rest API?

https://www.springboottutorial.com/spring-boot-versioning-for-rest-services

Asked about Agile method, how scrum works, how stories defines, how sprint defines and how to provide estimation.

What is HTTP protocol?

What is Docker and how does it work?

## Sapient
1. Design Elevator system? Define class structure and how will you use Queue?
2. What is the different between Abstraction and Encapsulation?
3. What are the different kinds of polymorphism?
4. What is Overriding and overloading in polymorphism?
5. What is Runtime and Compile time polymorphism?
6. What is inheritance?
7. Have you worked on some design patterns?
8. What is singleton design pattern?
9. Where have you used factory and abstract factory design pattern?
10. What is the best use of factory pattern? Why you are using Factory with DAO layer class.
11. What is the Exception hierarchy?
12. Is there any thing like compile time exception?
13. How will you create your custom checked exception?
14. How will you create custom unchecked exception class?
15. Have you worked on any immutable class? What is the concept the immutability? 
16. How to create immutable class?
17. What is cloning?
18. What is Shallow and Deep cloning?
19. What is serialization?How to achieve serialization?
20. How serialization works? What is the logic in behind it?
21. you are going to serialize class of employee class having property?
22. What are enums? Why enum needed? 
23. Is enum singleton?
24. How will you know Exception has been thrown from any thread you executed?
25. Do you know about garbage collection? Do you know how garbage algorithm works?
26. What is different algorithm JVM is using for garbage collection?
27. There is abstract class which can provide the definition of method, so what is the use of interface?
28. Do you know method references? Its a part of java 8.





