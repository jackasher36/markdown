# JSTL

JSTL出现可以用标签来代替java程序，以一种类似于Html语言的方式，主要还是想要实现前后端分离

这是一个foreach循环的tag

```html
 <tag>
        <description>
            The basic iteration tag, accepting many different
            collection types and supporting subsetting and other
            functionality
        </description>
        <name>forEach</name>
        <tag-class>org.apache.taglibs.standard.tag.rt.core.ForEachTag</tag-class>
        <tei-class>org.apache.taglibs.standard.tei.ForEachTEI</tei-class>
        <body-content>JSP</body-content>
        <attribute>
            <description>
                Collection of items to iterate over.
            </description>
            <name>items</name>
            <required>false</required>
            <rtexprvalue>true</rtexprvalue>
            <type>java.lang.Object</type>
            <deferred-value>
                <type>java.lang.Object</type>
            </deferred-value>
        </attribute>
        <attribute>
            <description>
                If items specified:
                Iteration begins at the item located at the
                specified index. First item of the collection has
                index 0.
                If items not specified:
                Iteration begins with index set at the value
                specified.
            </description>
            <name>begin</name>
            <required>false</required>
            <rtexprvalue>true</rtexprvalue>
            <type>int</type>
        </attribute>
        <attribute>
            <description>
                If items specified:
                Iteration ends at the item located at the
                specified index (inclusive).
                If items not specified:
                Iteration ends when index reaches the value
                specified.
            </description>
            <name>end</name>
            <required>false</required>
            <rtexprvalue>true</rtexprvalue>
            <type>int</type>
        </attribute>
        <attribute>
            <description>
                Iteration will only process every step items of
                the collection, starting with the first one.
            </description>
            <name>step</name>
            <required>false</required>
            <rtexprvalue>true</rtexprvalue>
            <type>int</type>
        </attribute>
        <attribute>
            <description>
                Name of the exported scoped variable for the
                current item of the iteration. This scoped
                variable has nested visibility. Its type depends
                on the object of the underlying collection.
            </description>
            <name>var</name>
            <required>false</required>
            <rtexprvalue>false</rtexprvalue>
        </attribute>
        <attribute>
            <description>
                Name of the exported scoped variable for the
                status of the iteration. Object exported is of type
                javax.servlet.jsp.jstl.core.LoopTagStatus. This scoped variable has nested
                visibility.
            </description>
            <name>varStatus</name>
            <required>false</required>
            <rtexprvalue>false</rtexprvalue>
        </attribute>
    </tag>
```

在maven项目引入改依赖后可使用JSTL

```html
<dependency>
     <groupId>jakarta.servlet.jsp.jstl</groupId>
     <artifactId>jakarta.servlet.jsp.jstl-api</artifactId>
     <version>2.0.0</version>
 </dependency>
<dependency>
    <groupId>org.glassfish.web</groupId>
    <artifactId>jakarta.servlet.jsp.jstl</artifactId>
    <version>2.0.0</version>
</dependency>
```

这个真的搞得我听懵逼的，这是两个公司的？ JST L就是把java程序封装成标签，让代码更像前端代码，只要是三个，判断，else if，循环

```html
<c:if test="empty _this variablility">
  
</c:if>
<!--这是if语句-->

<c:foreach items="_varability" var="_name">
  _name.if or something else
</c:foreach>

<c:choose>
	<c:when test="_name">
  
  </c:when>
  
  <c:otherwise>
  
  
  </c:otherwise>
</c:choose>

```

这样应该可以完成一些基本功能了