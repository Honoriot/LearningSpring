# Implementing Bean Lifecycle Using Annotations

- @PostConstruct
- @PreDestroy

To use this *@PostConstruct* and *@PreDestroy*, we need to add a dependency in our *pox.xml* file.

```xml
<dependency>
    <groupId>javax.annotation</groupId>
    <artifactId>javax.annotation-api</artifactId>
    <version>1.3.2</version>
</dependency>
```

First we will create a **Test** class with the annotation used with starting and ending of bean methods.

```java
class Test{
    ...
    @PostConstruct
    public void start(){print("Staring ...");}

    @PreDestroy
    public void end(){print("Ending ...");} 
}
```

By default annotaions are disable, now we have to enable anotations in the *config.xml* by adding a tag ***<context:annotation-config />***.

```xml
<beans>
    ...
    <context:annotation-config/>
    ...
</beans>
```
