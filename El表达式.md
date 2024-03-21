# El表达式

什么是el表达式，其实el是JSp的一种，在jsp中前端代嵌入后端代码是这样的：

```jsp
<a href="<%=request.getContextPath()%>"></a>
```

这看上去非常的乱，很不美观，所以我们可以使用更简洁的方式

```jsp
<a href="${contextPath}"></a>
```

这样看上去简洁许多，并且一眼看出这是一个变量，有意思的是，这里的contextPath其实是从get方法来的，而不是属性名，将get后面的变量首字母小写加入

默认从最小的域开始取数据，并输出到浏览器，当然我们也可 可以指定从某个域里面取数据

```cmd
${requestScope.contextPath}
${pageScope.contextPath}
${sessionScope.contextPath}
${applicationScope.contextPath}
```

el有一些影响参数可以直接使用

+ ```java
  pageContext
  //该参数可以调用Request
  pageContext.request.getContextPath
  ```

+ ```java
  param
  //该参数可以得到request里面的内容
  param._aihao
  //获取添加到request域里面的name=aihao&value=?
  request.getParamter("_name")
  //等同于该jsp语句
  ```

+ ```java
  initparam
  //该参数可获取文本域内容，对应jsp里面的application
  initparam._pageSize 
  //获取到context里面的内容，xml文本里面的信息
  application.getInitparamter("_name")
  //等同于该JSP语句
    
  request.getContext()
  //等同于该servlet语句
    
  ```

由于EL只解决了变量问题，让java变量更像html了，但是接受数据的代码还是得写在JSP中，为了更加简化所以我们引入了JSFL（JAVA STANDARD TAG LIB），用标签来代表大量的java代码

el就像是在html里面取变量元素一样${_variblity_name}就可以拿到域中的对象或数据