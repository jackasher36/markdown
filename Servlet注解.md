# Servlet注解

+ 注解格式  @_注解名称(name = value)

```java
@WebServlet(name = "hello", urlpatterns = {"/hello"}, loadOnStartup = 1, initParams = {@WebInitParam(name = "driver", value = ""), @WebInitParam(name = "driver", value = "") );
                                                                                       
简单配置即可
  @WebServlet(name = "list", urlpatterns{"/hello"});
```

 