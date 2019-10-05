1. What is a transient variable?

Ans: Transient variables are not serializable. It helps to avoid a variable to being serialization.

2. Write the code to initialize the inner class members.
 ```
 public class OuterClass {

      class InnerClass{
            private int age;
           
            public void display(){
                  System.out.println("Age="+age);
            }
      }
      /**
       * @param args
       */
      public static void main(String[] args) {
            OuterClass.InnerClass innerObj=new OuterClass().new InnerClass();
            innerObj.age=20;
            innerObj.display();
      }
}
```
3. What is static and instance variable and methods?

Ans: Static variables are per class but the instance variables are per object. All object share a single copy of static variable. In case of static method , no need of object creation for calling static method. The static method can directly call by using class name. Instance method need object for calling.

4. What is Dynamic loading and static loading?

Ans: Dynamic class loading is by Class.forName() , which loads the class dynamically(during runtime). Also you can use reflection for dynamic class loading. But, the static class loading is working by using ‘new’ keyword.
E.g.One common example is trivial JDBC programming. Dynamic classloading is used to load the driver class

5. What type of loading is class.forName()?

Ans: Its dynamically locate and loads the class.

6. What is hibernate 3 main benefits?

Ans: There are many benefits of hibernate. But the most benefits are below :-
1.     It reduces the developer effort to writing queries.
2.     Its easy to use with relational object which maps with java class and database relation.
3.     Query tuning is not required and it implements separates cache which is reason for better performance.

7. I have 100 tables and fields. I want to find one table name and  column names.  Write a quey.
Ans: select TABLE_SCHEMA,TABLE_NAME,COLUMN_NAME from information_schema.COLUMNS where TABLE_NAME='EMPLOYEE';

8. How to define a field name in hibernate using annotation ?

Ans: @Column  (Its provided by java persistent  API).

9. What is Synchronization ?
Ans: Synchronization is a solution for concurrency issue. Java provide 'synchronized' keyword for implementing this.

10. The most commonly used classes in collections ?
Ans: ArrayList, LinkedList, HashTable, HashMap and ConcurrentHashMap, etc

11. What are the types of classLoader in java?

Ans: As per my knowledge there are basically 3 types of class loader like bootstarp classloader,extension class loader and system class loader.

**Bootstrap Class Loader**
Bootstrap class loader loads java’s core classes like java.lang, java.util etc. These are classes that are part of java runtime environment. Bootstrap class loader is native implementation and so they may differ across different JVMs.

**Extensions Class Loader**
**JAVA_HOME/jre/lib/ext** contains jar packages that are extensions of standard core java classes. Extensions class loader loads classes from this ext folder. Using the system environment propery java.ext.dirs you can add ‘ext’ folders and jar files to be loaded using extensions class loader

**System Class Loader**
Java classes that are available in the java classpath are loaded using System class loader

https://www.geeksforgeeks.org/classloader-in-java/ 

12. What is difference between static and init block in java

Ans: Static does not need any object to execute. Before creating any object the static block can execute as we are using in static method. So, here the static block is call at the time of JVM execution , means before creating the object( when first time JVM execute ). But Initialization block is   call/loaded every time when object is created.Whenever the object is created at that time the Initialization block is loaded.
```
public class InitBlockStaticBlock {

    /*
     * Static block
     */
    static{
        System.out.println("I am here in static");
    }
   
    /*
     * INIT block
     */
    {
        System.out.println("I am here in INIT ");
    }
   
    /**
     * @param args
     */
    public static void main(String[] args) {
        InitBlockStaticBlock obj1=new InitBlockStaticBlock();
        InitBlockStaticBlock obj2=new InitBlockStaticBlock();
        InitBlockStaticBlock obj4=new InitBlockStaticBlock();

    }

}


Out put :-
I am here in static
I am here in INIT
I am here in INIT
I am here in INIT
```

13. How ConcurrentHashMap works?

Ans: The basic design of ConcurrentHashMap is to handling threading. Basically it locks each of the box (by default 16) which can be locked independently and thread safe for operation. And it does not expose the internal lock process.

14. Can a static block throw exception?

Ans: Yes. We can throw checked exception.

15. What is difference between iterator access and index access?

Ans : Basically iterator access process the traverse operation through each element, where index access process access direct the element by using the index.

16.  Why character array is better than string for storing password in java?

Ans : Because, character array stores data in encrypted format which is not readable by human. But,the string stores the data in human readable format which is not secure.

17. what is daemon thread in java ?

Ans : A daemon thread is normally runs on background. And it does not prevent the JVM from exiting when the program finishes but the thread is still running.

18. What is Java Reflection API?

Ans  : Reflection is one of the most powerful api which help to work with classes, methods and variables  dynamically. Basically it inspect the class attributes at runtime. Also we can say it provides a metadata about the class. 

19. What is the difference between Serializable and Externalizable interfaces? 

Ans : Both interfaces are used for implement serialization. But, the basic difference is Serializable interface does not have any method (it’s a marker interface ) and Externalizable interface having 2 methods such as readExternal() and writeExternal(). Serializable interface is the super interface for Externalizable interface. 

20. IOC,DI,Factory,Singleton
Ans:
IOC (Inversion Of Controller): Giving control to the container to get an instance of the object is called Inversion of Control., means instead of you are creating an object using the new operator, let the container do that for you.

DI (Dependency Injection): Way of injecting properties to an object is called Dependency injection.

We have three types of Dependency injection
    1)  Constructor Injection
    2)  Setter/Getter Injection
    3)  Interface Injection
Spring will support only Constructor Injection and Setter/Getter Injection.

Factory Pattern: we create object without exposing the creation logic to the client and refer to newly created object using a common interface. 

https://www.tutorialspoint.com/design_pattern/factory_pattern.htm#

Singleton: This pattern involves a single class which is responsible to create an object while making sure that only single object gets created.

We're going to create a SingleObject class. SingleObject class have its constructor as private and have a static instance of itself.

https://www.tutorialspoint.com/design_pattern/singleton_pattern.htm

21. Do you know pass by reference or pass by value? how does Java do it?  
Ans:Java is always pass-by-value. Unfortunately, when we pass the value of an object, we are passing the reference to it. This is confusing to beginners.

It goes like this:
```
public static void main(String[] args) {
    Dog aDog = new Dog("Max");
    Dog oldDog = aDog;

    // we pass the object to foo
    foo(aDog);
    // aDog variable is still pointing to the "Max" dog when foo(...) returns
    aDog.getName().equals("Max"); // true
    aDog.getName().equals("Fifi"); // false
    aDog == oldDog; // true
}

public static void foo(Dog d) {
    d.getName().equals("Max"); // true
    // change d inside of foo() to point to a new Dog instance "Fifi"
    d = new Dog("Fifi");
    d.getName().equals("Fifi"); // true
}
```

In the example above aDog.getName() will still return "Max". The value aDog within main is not changed in the function foo with the Dog "Fifi" as the object reference is passed by value. If it were passed by reference, then the aDog.getName() in main would return "Fifi" after the call to foo.

https://stackoverflow.com/questions/40480/is-java-pass-by-reference-or-pass-by-value

22: lazy loading vs eager loading 
Ans:

23: how is a state of a stateful session bean achieved  
Ans:

24: how would you put a button that would not submit an html  form? what needs to be done so that when you press the button it would not submit the form?
Ans:

25: interface vs abstract class
26-Map vs set 
27-Rest api methods 
28-java 8 features 
29-continuous integration 
30-dependency injection 
31-sorting an object 
32-comparable interface 
33-hashcode vs equals 
34- Polymorphism-runtimevs compiletime
overriding->rntime
overloading->compiletime
35-Difference between web server and application server

36-what is default constructor  

37-what are oops concepts  

38-Whats are runtime exceptions and exceptions

39-Transative dependency,Cyclic dependency  

40-Hibbernate mapping, 

41-Spring Boot

42-arraylist vs linkedList

43- Fail fast vs Fail safe

44- memory management?
Ans- https://www.geeksforgeeks.org/java-memory-management/

45- In which folder projects are hosted/deployed in tomcat/Jboss?
Ans- **Tomcat-->** webApp folder
     **JBoss-->** JBoss installation directory at standalone/deployments

46- Clean vs build in maven
Ans- 

47- EAR vs WAR vs JAR
Ans- 
In J2EE application, modules are packaged as EAR, JAR and WAR based on their functionality

JAR: EJB modules which contain enterprise java beans (class files) and EJB deployment descriptor are packed as JAR files with .jar extenstion

WAR: Web modules which contain Servlet class files, JSP Files, supporting files, GIF and HTML files are packaged as JAR file with .war (web archive) extension

EAR: All above files (.jar and .war) are packaged as JAR file with .ear (enterprise archive) extension and deployed into Application Server.


A WAR (Web Archive) is a module that gets loaded into a Web container of a Java Application Server. A Java Application Server has two containers (runtime environments) - one is a Web container and the other is a EJB container.

The Web container hosts Web applications based on JSP or the Servlets API - designed specifically for web request handling - so more of a request/response style of distributed computing. A Web container requires the Web module to be packaged as a WAR file - that is a special JAR file with a web.xml file in the WEB-INF folder.

An EJB container hosts Enterprise java beans based on the EJB API designed to provide extended business functionality such as declarative transactions, declarative method level security and multiprotocol support - so more of an RPC style of distributed computing. EJB containers require EJB modules to be packaged as JAR files - these have an ejb-jar.xml file in the META-INF folder.

Enterprise applications may consist of one or more modules that can either be Web modules (packaged as a WAR file), EJB modules (packaged as a JAR file), or both of them. Enterprise applications are packaged as EAR files ― these are special JAR files containing an application.xml file in the META-INF folder.

Basically, EAR files are a superset containing WAR files and JAR files. Java Application Servers allow deployment of standalone web modules in a WAR file, though internally, they create EAR files as a wrapper around WAR files. Standalone web containers such as Tomcat and Jetty do not support EAR files ― these are not full-fledged Application servers. Web applications in these containers are to be deployed as WAR files only.

In application servers, EAR files contain configurations such as application security role mapping, EJB reference mapping and context root URL mapping of web modules.

Apart from Web modules and EJB modules, EAR files can also contain connector modules packaged as RAR files and Client modules packaged as JAR files.

48- Can I use HTTP PUT to create resource?
Ans- It's quite possible, valid and even preferred in some occasions, to use PUT to create resources, or use POST to update resources. Use PUT when you can update a resource completely through a specific resource.

restcookbook.com › HTTP Methods › put-vs-post

https://stackoverflow.com/questions/107390/whats-the-difference-between-a-post-and-a-put-http-request

49. Monolithic vs Microservice artitecture?

Ans-

50- Marshelling vs Unmarshelling

Ans-

51. What will be output?
```
class Test{
void foo(int a,long b){
}
void foo(long a,int b){
}

public static void main(String args[]){
 Test obj = new Test();
 obj.foo(10,10);
}
```
Compilation error #stdin compilation error #stdout 0s 0KB
Main.java:20: error: reference to foo is ambiguous
		o.foo(1,1);
		 ^
  both method foo(int,long) in Ideone and method foo(long,int) in Ideone match
1 error


}
Test obj = new Test
                
  
