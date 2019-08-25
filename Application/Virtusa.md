## Rate :: **2/5**

1. classnotfoundexception vs noclassdeffounderror
2. Design Pattern in Spring
3. Difference between create an object with new keywork vs Spring is creating object using xml configuration
4. What is the output of below code
```
  class A{
    void foo(){
    }
  }
  class B extends A{
    void bar(){
    }
    public static void main(String args[]){
    A obj = new B();
    obj.foo();
    obj.bar();

    B ob = new A();
    ob.foo();
    ob.bar();
    }
    }
  ```
  **Ans: Compile time type== is the declared type of variable (decides eligible methods to called); RunTime type==type of object variable is pointing to**
  
  Eg. A obj = new B();// Here compile time type of obj == A and runtime type of object is B;
  
   **A obj = new B();// compile time type = A and runtime type = B;** this declaration makes all the methods of A elligible for calling but compiler will not find bar() method during compilation as it is not the method of class A. Hence, ob.bar()--> failed to compile
  
  if below eclarion is possible
  
  **So B ob = new A(); compile time type= B and runtime type = A;** B ob ==> all the methods of B elligible for calling but at runtime ob will be pointing to object of A, and a dont't have all the methods of B so it will create runtime error.
   
  
  5. Java is pass by value or pass by refernce example.
  6. How memory is allocated while creating an object.
  7. Top most class of Exception class.
  8. Local vs memeber inner class
  9. Singleton design pattern
  10. String vs StringBuffer vs StringBuilder
  11. compareTo()..
  12. Example of Deadlock.
  13. IOC vs DI
  14. Program for Linear Search
  15. Program to craete Test for method of local inner class method
  
 ## TakeAway-->**ALWAYS PRACTICE THE BASIC**
  
  Reason for Not selection: Basic was not up to date
  
