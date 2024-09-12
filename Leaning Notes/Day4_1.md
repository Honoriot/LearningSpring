# Constructor Injection
Till now the bean injection we are doing, it is by default setter injection. Now we will perform constructor injection. We are creating *Person* class.

## When we have only single constructot inside class
```java
public class Person{
    private String name;
    private id personId;
    private Address address;
    public void Person(String name, int personId, Address address){
        this.name = name;
        this.personId = personId;
        this.address = address;
    }
    ...
}
```

Now we had created a basic *Person* class. Now we will create bean in config.xml.
```xml
<bean class="" name="personAddress" >
<bean class="exactClassNameWithPackage" name="person1">
    <constructor-arg name="name" value="..." />
    <constructor-arg name="personId" value="..." />
    <constructor-arg name="address" ref="personAddress"/>
</bean>
```

To add *c schema*, use this. C schame make in bean craetion easy.
```xml
<beans xmlns:c="http://www.springframework.org/schema/c">

<bean class="" name="personAddress" >
<bean class="exactClassNameWithPackage" name="person1" c:name="..." c:personId="" c:address-ref="">
</bean>

``` 

## When we have more than one construtor in a class

First create an *Addition* class with more then one parametarized constructor.

```java
public class Addition{
    Addition(int num1, int num2){print(num1 + num2);}
    Addition(double num1, int num2){print(num1 + num2);}
    Addition(String num1, String num2){print(num1 + num2);}
}
```
Now to solve this problem, we have *type* property, we can also provide *index* number;
```xml
<beans>
    <bean class="" name="">
        <constructor-arg name="num1" type="int" index="1" value="10">
        <constructor-arg name="num2" type="int" index="2" value="20">
    </bean>
    <bean class="" name="">
        <constructor-arg name="num1" type="double" index="1" value="10">
        <constructor-arg name="num2" type="int" index="2" value="20">
    </bean>
    <bean class="" name="">
        <constructor-arg name="num1" type="String" index="1" value="10">
        <constructor-arg name="num2" type="String" index="2" value="20">
    </bean>
</beans>
```

***HAPPY LEARNING***  
[**Click**](/Leaning%20Notes/Day4_2.md) for Next Day