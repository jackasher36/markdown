# Servlet Request

+ servlet请求域对象只在每次请求生效（http协议内容），两次请求时想要第二个servlet请求使用第一个请求域需要使用转发器

+ ```java
  RequestDispather dispather = request.getRequestDispather("/b");
  //Get dispather Object first
  dispather.forward(request,reponse);
  //use forward method in dispather sencondly
  ```

+ 注意到参数中传的是路径意味着所有资源都可以转发，至于路径从哪个根开始，还没搞清......

+ 关于request的两个方法  

  + ```java
    String usrname = request.getParameter("username");
    //uri?username=leo&paawd=123&sex=1
    Object obj = request.getAttribute("name");
    //After setAttribte
    
    //The first one is to get data from browser
    //the second one is to get request attribute data
    ```

+ Request底层是Map集合，一个key一个value，Tomcat帮我们封装，相应的http协议内容以封装好

+ 如何解决Post乱码问题    

  + ```java	
    request.setCharacterEncoding("UTF-8");
    response.setContext("text/html;charset=utf-8");
    //this is the soultion for post method only
    ```

  + ```java
    request.setCharacterEncoding("UTF-8");
    response.setContext("text/html;charset=utf-8");
    //this is the soultion for post method only
    ```

+ request其他常用方法

  + ```java
    String method = request.getMethod();
    //Get http method
    ```

  + ```java
    String requestURI = request.getRequestURI();
    //Get request httpd  method (get/post)
    ```

  + ```java
    String servletPath = request.getServletPath();
    //Get servlet Project Path
    ```

  ------

  
