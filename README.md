# Spring---Bean-Life-Cycle
lifecycle of a bean consists of several phases, which are managed by the container. Here is an overview of the bean lifecycle phases.

![sdsad drawio](https://user-images.githubusercontent.com/73180409/228131981-531c245c-8a21-4375-aee4-f38fa166d4dc.png)

Bean life cycle is managed by the spring container. When we run the program then first of all the spring container start, after that the container create the instance of a bean as per the request, and then dependencies are injected, And finally the bean is destroyed when the spring container is closed.

- Container Started 

- Bean instantiation: 
In this step, the Spring container creates an instance of the bean class. It does this by calling the default constructor of the bean class.

- Dependency injection: 
In this step, the Spring container injects the dependencies of the bean. Dependencies are other beans that the current bean depends on to function correctly. Dependency injection can be done using constructor injection, setter injection, or field injection.

- Bean initialization & Custome Init: 
In this step, the Spring container initializes the bean. It calls the bean's initialization methods such as the afterPropertiesSet() method (if the bean implements the InitializingBean interface), or the init() method (if the bean is annotated with the @PostConstruct annotation). These methods are used to perform any necessary setup or initialization tasks for the bean.

- Bean ready for use: 
In this step, the bean is now ready for use. The bean can now be used by other beans or by the application.

- Bean destruction: 
In this step, the Spring container destroys the bean. It calls the bean's destruction methods such as the destroy() method (if the bean is annotated with the @PreDestroy annotation), or the destroy() method (if the bean implements the DisposableBean interface). These methods are used to perform any necessary cleanup tasks for the bean.


> **_Note_** Bean life cycle is managed by the spring container. When we run the program then first of all the spring container start, after that the container create the instance of a bean as per the request, and then dependencies are injected, And finally the bean is destroyed when the spring container is closed.


# Properties & Description

| Sr. No  | Properties   | Description    |
| ------------- | ------------- | ------------- |
| 1  | Class  | This attribute is mandatory and specifies the bean class to be used to create the bean.|
| 2  | Name  | This attribute specifies the bean identifier uniquely. you use the id and/or name attributes to specify the bean identifier(s). |
| 3  | Scope | This attribute specifies the bean identifier uniquely. you use the id and/or name attributes to specify the bean identifier(s). |
| 4  | Constructor-arg  | This is used to inject the dependencies. |
| 5  | Properties  | This is used to inject the dependencies |
| 6  | Auto wiring  | This is used to inject the dependencies |
| 7  | lazy-initialization | A lazy-initialized bean tells the IoC container to create a bean instance when it is first requested, rather than at the start-up. |
|    |  | |
 
 
 # Bean Scopes
| Sr. No  | Properties   | Description    |
| ------------- | ------------- | ------------- |
| 1  | Singleton  | This scopes the bean definition to a single instance per Spring IoC container (default).|
| 2  | Prototype  | This scopes a single bean definition to have any number of object instances.|
| 3  | Request | This scopes a bean definition to an HTTP request. Only valid in the context of a web-aware Spring ApplicationContext. |
| 4  | Session  | This scopes a bean definition to an HTTP session. Only valid in the context of a web-aware Spring ApplicationContext. |
| 5  | global-session  | This scopes a bean definition to a global HTTP session. Only valid in the context of a web-aware Spring ApplicationContext. |
|    |  | |
 
 
 # The singleton scopes
 
 If a scope is set to singleton, the Spring IoC container creates exactly one instance of the object defined by that bean definition allows only one instance to be created and provides global access to all other classes through this single object or instance.
 
1. @Component: When a bean is annotated with @Component, it is created as a Singleton by default. This means that the same instance of the bean is shared across the entire application context.

2. @Service: Similar to @Component, beans annotated with @Service are created as Singleton by default.

3. @Repository: Beans annotated with @Repository are also created as Singleton by default.

4. @Controller: Beans annotated with @Controller are created as Singleton by default.

5. To override the default Singleton scope and specify a different scope for a bean, you can use the @Scope annotation. For example:
```java
@Component
@Scope("prototype")
public class MyPrototypeBean {
  // ...
}
```
The MyPrototypeBean class is annotated with @Scope("prototype"), which means that a new instance of the bean will be created every time it is requested from the Spring container.


# The prototype scopes
If the scope is set to prototype, the Spring IoC container creates a new bean instance of the object every time a request for that specific bean is made.

To define a bean with the Prototype scope, you can use the @Scope annotation with the value "prototype", like this:

```java
@Component
@Scope("prototype")
public class MyPrototypeBean {
  // ...
}
```

In this example, the MyPrototypeBean class is annotated with @Scope("prototype"), which specifies that a new instance of the bean will be created every time it is requested by the application.

> **_Note_** It is important to note that beans with Prototype scope are not managed by the Spring container after they are created. This means that Spring will not call any lifecycle methods (such as @PostConstruct or @PreDestroy) on the bean, and it is the responsibility of the application to manage the lifecycle of the bean.
