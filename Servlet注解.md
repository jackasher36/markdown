# Servlet注解

+ 注解格式  @_注解名称(name = value)

```java
@WebServlet(name = "hello", urlpatterns = {"/hello"}, loadOnStartup = 1, initParams = {@WebInitParam(name = "driver", value = ""), @WebInitParam(name = "driver", value = "") );
                                                                                       
简单配置即可
  @WebServlet(name = "list", urlpatterns{"/hello"});
```
![Images](https://github.com/jackasher36/markdown/blob/main/images/%E6%88%AA%E5%B1%8F2024-03-15%2017.06.54.png)

 
<<<<<<< HEAD
=======
<<<<<<< HEAD
=======
>>>>>>> e4435b7baa482cc5de3a840cf518a8978c8dd5a5

![Images](https://github.com/jackasher36/markdown/blob/main/images/%E6%88%AA%E5%B1%8F2024-03-15%2017.06.54.png)

+ 有个更简单的

+ ```java
  @WebServlet("/hello");
  ```

<<<<<<< HEAD
+ 但本质其实都是web.xml
=======
+ 但本质其实都是web.xml
>>>>>>> ae428b1 (2024-4-16)
>>>>>>> e4435b7baa482cc5de3a840cf518a8978c8dd5a5
