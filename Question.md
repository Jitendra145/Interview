## Multiple postconstruct and predestroy methods.

```
@PreDestroy
public void destroyBean() {
System.out.println("Start: PlaceBidBean.destroy()");
System.out.println("Inside destroy, PreDestroy, PrePassivate");
System.out.println("End: PlaceBidBean.destroy()");
}
  
@PostConstruct
public void initBean() {
System.out.println("Start: PlaceBidBean.initBean()");
System.out.println("Inside init: PostConstruct, PostActivate");
System.out.println("End: PlaceBidBean.initBean()");
}
  
@PostConstruct
public void initializeBean() {
System.out.println("Start: PlaceBidBean.initializeBean()");
System.out.println("Inside init: PostConstruct, PostActivate");
System.out.println("End: PlaceBidBean.initializeBean()");
}
```

Is it possible to have multiple postconstruct and predestroy methods as mentioned above?

**Ans:**
You can have mutiple callbacks for a given bean.It is correct.

But the condition is you cannot define mutiple callback methods for a single lifecycle event in a Single bean class

Ex. In the above example, you mentioned 2 callback methods initBean() and initializeBean() for a PostConstuct event in 1 bean class PlcaeBidBean. This is wrong 

However you can remove the one of the postConstruct methods and can put it in bean superclass or also in Bean Interceptor classes so that both methods will be called.

Simply to say, atmost 1 lifecycle callback method should be declared for each lifecycle event in each class ( it can be bean class or its super class or its interceptor class)

## Configure multiple view resolvers priority in Spring MVC
### Problem
In Spring MVC application, often times, you may applying few view resolver strategies to resolve the view name. For example, combine three view resolvers together : InternalResourceViewResolver, ResourceBundleViewResolver and XmlViewResolver.

```
<beans ...>
	<bean class="org.springframework.web.servlet.view.XmlViewResolver">
	      <property name="location">
	         <value>/WEB-INF/spring-views.xml</value>
	      </property>
	</bean>

	<bean class="org.springframework.web.servlet.view.ResourceBundleViewResolver">
	      <property name="basename" value="spring-views" />
	</bean>
	
	<bean id="viewResolver"
	      class="org.springframework.web.servlet.view.InternalResourceViewResolver" >
              <property name="prefix">
                 <value>/WEB-INF/pages/</value>
              </property>
              <property name="suffix">
                 <value>.jsp</value>
              </property>
        </bean>
</beans>
```

**Solution:** If multiple view resolver strategies are applied, you have to declare the priority through “order” property, where the lower order value has a higher priority, for example :

```
<beans ...>
	<bean class="org.springframework.web.servlet.view.XmlViewResolver">
	     <property name="location">
	        <value>/WEB-INF/spring-views.xml</value>
	     </property>
	     <property name="order" value="0" />
	</bean>

	<bean class="org.springframework.web.servlet.view.ResourceBundleViewResolver">
	     <property name="basename" value="spring-views" />
	     <property name="order" value="1" />
	</bean>
	
	<bean id="viewResolver"
	      class="org.springframework.web.servlet.view.InternalResourceViewResolver" >
              <property name="prefix">
                 <value>/WEB-INF/pages/</value>
              </property>
              <property name="suffix">
                 <value>.jsp</value>
              </property>
	      <property name="order" value="2" />
        </bean>
</beans>
```

Now, if a view name is returned, the view resolving strategy works in the following order :

```
XmlViewResolver --> ResourceBundleViewResolver --> InternalResourceViewResolver
```

**Note:

The InternalResourceViewResolver must always assign with the **lowest priority (largest order number)**, because it will resolve the view no matter what view name is returned. It caused other view resolvers have no chance to resolve the view if they have lower priority.

Q. What do you mean by Spring Singleton Scope?

A. tell me what the output of the following program would be."

Spring.xml

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
    http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="scopeTest" class="com.example.scope.Scope" scope="singleton">
        <property name="name" value="Shamik Mitra"/>    
    </bean>    
    <bean id="scopeTestDuplicate" class="com.example.scope.Scope" scope="singleton">
        <property name="name" value="Samir Mitra"/>    
    </bean>
</beans>
```

**Scope.java**

```

package com.example.scope;
public class Scope {
    private String name;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return "Scope [name=" + name + "]";
    }
}
```

**Main.java**
```
package com.example.scope;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Main {
    public static void main(String[] args) {
        ApplicationContext ctx = new ClassPathXmlApplicationContext(
            "configFiles/Scope.xml");
        Scope scope = (Scope) ctx.getBean("scopeTest");
        Scope scopeDuplicate = (Scope) ctx.getBean("scopeTestDuplicate");
        System.out.println(scope == scopeDuplicate);
        System.out.println(scope + "::" + scopeDuplicate);
    }
}
```
**OUTPUT:**

```
Reference Check ::false
Scope [name=Shamik Mitra]::Scope [name=Samir Mitra]
```

According to the Spring documentation:

"When a bean is a singleton, only one shared instance of the bean will be managed, and all requests for beans with an id or ids matching that bean definition will result in that one specific bean instance being returned by the Spring container.

To put it another way, when you define a bean definition and it is scoped as a singleton, then the Spring IoC container will create exactly one instance of the object defined by that bean definition. This single instance will be stored in a cache of such singleton beans, and all subsequent requests and references for that named bean will result in the cached object being returned."

In my example, I use two different ids (scopeTest and ScopeTestDuplicate), so the Spring container creates two instances of the same class and binds them with respective ids, then stores them in a Singleton cache.

You can think of a Spring container as managing a key-value pair, where the key is the id or name of the bean and the value is the bean itself. So, for a given key, it maintains a Singleton. So if we use that key as a reference to or of other beans, the same bean will be injected to those other beans.

In summation, Spring guarantees exactly one shared bean instance for the given id per IoC container, unlike Java Singletons, where the Singleton hardcodes the scope of an object such that one and only one instance of a particular class will ever be created per ClassLoader.




