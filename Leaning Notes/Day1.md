# What is Spring?
Spring is a Dependency Injection framework to make java application loosely coupled.
Spring framework makes the easy development of JavaEE application.

# Dependency Injection
It is a design pattern.

```java
class Geeta{
    public void doWork(){...}
}
// Ramu class is dependent on Geeta Class, this is known is dependency
class Ramu{
    Geeta object;
    public void doWork(){...}
}
```

# Spring Modules
- Spring Core
    - Core
    - Beans
    - Context
    - spEl(Spring Expression language)
- AOP : Asspect Oriented Programing
- Aspect
- Instrumention
- Messaging
- Data Acccess/Integration
    - JDBC : Java Database Connectiviy
    - ORM : Object Relational Mapping
    - JMS : Java Messaging Services
    - OXM : Object XML Mapping
- Web Module
    - web
    - servlet
    - Portlet
    - WebSocket and many more.
- Test Module

# Spring IOC(Inversion Of Control) Container
It creates the objects, configures and assembles their dependencies, manages there entire lifecycle.
- Create the object
- Hold the object in the memory
- Inject one object into another object as per need
- Maintain the lifecycle of object

### Important parts for IOC
- **Beans** 
- **Config**

## ApplicationContext 
It is an interface. So we cannot creat obbject for this.
Classes that implements this interface.
- ClasspathXMLApplicationContext   
    It scans and search for XML config in java class path
- AnnotationConfigApplicationContext  
    It searches for the beans, for which we use annotations
- FileSystemXMLApplicationContext  
    It searches for the XML config files from the filesystem

## Types of Injecting Dependencies
### Setter Injection

```java 
// dommy code
class Student{
    id, name, address;
    setId(id){};
    setname(name){};
    setAddress(address){};
}
class Address {
    street, city, state, country;
    setStreet(street);
    setCity(city);
    setState(state);
    setCountry(country);
}
```
### Constructor Injection
```java
class Student{
    id, name, address;
    Student(id, name, address){};
}
class Address{
    street, city, state, country;
    Address(street, city, state, country){};
}
```

## Configuration File
Where we declare beans and its dependency.