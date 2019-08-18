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


