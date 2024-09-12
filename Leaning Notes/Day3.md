# Injecting varoius collection types using bean

## Injecting Primitive Types:

```xml
<bean class="" name="">
    <property name="">
        <value>value</value>
    </property>
</bean>

<bean class="" name="">
    <property name="" value="" />
    <property name="" value="" />
</bean>

<bean class="" name="" p:property="">
```

## Injecting Collection Types

### **List**

```xml
<bean>
    <property name="">
        <list>
            <value>value1</value>
            <value>value2</value>
            <null/>
            ...
        </list>
    </property>
</bean>
```

### **SET**

```xml
<bean>
    <property name="">
        <set>
            <value>value1</value>
            <value>value2</value>
            <null/>
            ...
        </set>
    </property>
</bean>
```

### **MAP**

```xml
<bean>
    <property name="">
        <map>
            <entry key="" value="" />
            <entry key="" value="" />
            ...
        </map>
    </property>
</bean>
```
## Injecting Properties

```xml
<bean>
    <property name="">
        <prop key="">value</prop>
        ...
    </property>
</bean>
```

## Injecting Reference Type

Consider two classes *class A* and *class B*. Class *A* is dependent on class *B*

```java
class A{
    private int id;
    private B objectB;
}
class B{
    private int id;
}
```
For this case we need to create a reference bean of *B* that can be passes to bean property of *A*.

```xml
<bean class="B" name="objectB" p:id="1789"/>

<bean class="A" name="objectA" p:id="2567">
    <property name="objectB">
        <ref bean="objectB"/>
    </property>
</bean>
```

***HAPPY LEARNING***  
[**Click**](/Leaning%20Notes/Day4_1.md) for Next Day