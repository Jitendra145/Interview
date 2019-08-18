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
