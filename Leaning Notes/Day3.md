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