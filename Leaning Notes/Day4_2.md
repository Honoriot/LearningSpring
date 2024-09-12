# Life Cycle Methods

Spring provides two important methods to every bean
- **public void init()**  
Initialization code usecases for loading, config, conntecting DB, Webservice etc.  
- **public void destroy()**  
To clean up code.

> We can change the name of these(init() and destroy()) method, but the signature must be the same.

## Life Cycle Flow

When you provide your bean to Spring, means to provide the bean class and config.xml file that is containing metadata about your bean class.

- First it will creat the Object
- Second it will set the value of bean, as per config file
- Third it will call *init()* method.
- Fourth you can use(read or any other type of activity on your bean).
- Fifth it will call for *destroy()* method, to clean up the code.

## Configuration Techniques
- XML
- Spring Interface
- Annotation

### Implementing Lifecycle methods Using **XML**

First we will create a **Test** class and create *init()* and *destroy()* method in it.
```java
class Test{
    public void init(){print("Getting Init");}
    public void destroy(){print("Getting destroyed");}
    ...
}
```

Now configuring *init* and *destroy* methods in config.xml file.
```xml
<bean class="" name="" init-method="init" destroy-method="destroy" ... />
```

Now attaching this config bean with main application.
```java
import org.springframework.context.support.AbstractApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
class App{
    AbstractApplicationContext context = new ClassPathXmlApplicationContext("config.xml");

    Test test = (Test) context.getBean("BeanName");
    context.registerShutdownHook(); // hook to execute bean destroy()
}
```
### Implementing Lifecycle methods Using **Interface**

First we will create **Test** class. In this case our class will implement ***InitializingBean*** interface.

```java
import org.springframework.beans.factory.InitializingBean;
import org.springframework.beans.factory.DisposableBean;
class Test implements InitializingBean, DisposableBean{
    ...
    public void afterPropertiesSet() throws Exception{
        // init method
        print("Initializing Bean");
    }
    public void destroy() throws Exception{
        // destroy method
        print("Destroy Bean");
    }
}
```

In this case of implementing interface lifecycle method, you don't need to add any init or destroy behavoir in your config.xml file.

```java
import org.springframework.context.support.AbstractApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
class App{
    AbstractApplicationContext context = new ClassPathXmlApplicationContext("config.xml");

    Test test = (Test) context.getBean("BeanName");
}
```
Interface implementation will automatically call the init method -> *afterPropertiesSet()* and destroy method -> *destroy()* after and befor of using bean.

***HAPPY LEARNING***  
[**Click**](../README.md) for Next Day