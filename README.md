# Spring---Bean-Life-Cycle
lifecycle of a bean consists of several phases, which are managed by the container. Here is an overview of the bean lifecycle phases.

![sdsad drawio](https://user-images.githubusercontent.com/73180409/228131981-531c245c-8a21-4375-aee4-f38fa166d4dc.png)

Bean life cycle is managed by the spring container. When we run the program then first of all the spring container start, after that the container create the instance of a bean as per the request, and then dependencies are injected, And finally the bean is destroyed when the spring container is closed.

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
 
