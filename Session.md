# Session

当我们创建session对象，浏览器第一次的请求和响应是这样的

下面为请求头

+ ```http
  Accept:
  text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8
  Accept-Encoding:
  gzip, deflate, br
  Accept-Language:
  zh-CN,zh
  Connection:
  keep-alive
  Cookie:
  MM_WX_NOTIFY_STATE=1; MM_WX_SOUND_STATE=1
  Host:
  localhost:8080
  Sec-Ch-Ua:
  "Chromium";v="122", "Not(A:Brand";v="24", "Brave";v="122"
  Sec-Ch-Ua-Mobile:
  ?0
  Sec-Ch-Ua-Platform:
  "macOS"
  Sec-Fetch-Dest:
  document
  Sec-Fetch-Mode:
  navigate
  Sec-Fetch-Site:
  none
  Sec-Fetch-User:
  ?1
  Sec-Gpc:
  1
  Upgrade-Insecure-Requests:
  1
  User-Agent:
  Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
  //这是请求头
  ```

下面为响应头：

+ ```http
  Connection:
  keep-alive
  Content-Length:
  57
  Date:
  Mon, 18 Mar 2024 07:54:06 GMT
  Keep-Alive:
  timeout=20
  Set-Cookie:
  JSESSIONID=C8D3160AB2F26FC1A9625F1595159138; Path=/oa; HttpOnly
  //这是响应头
  ```

当我们第二次再向浏览器请求时，应该拿到的是的同一个session对象

//请求头：

+ ```http
  Accept:
  text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8
  Accept-Encoding:
  gzip, deflate, br
  Accept-Language:
  zh-CN,zh
  Connection:
  keep-alive
  Cookie:
  MM_WX_NOTIFY_STATE=1; MM_WX_SOUND_STATE=1; JSESSIONID=C8D3160AB2F26FC1A9625F1595159138
  Host:
  localhost:8080
  Sec-Ch-Ua:
  "Chromium";v="122", "Not(A:Brand";v="24", "Brave";v="122"
  Sec-Ch-Ua-Mobile:
  ?0
  Sec-Ch-Ua-Platform:
  "macOS"
  Sec-Fetch-Dest:
  document
  Sec-Fetch-Mode:
  navigate
  Sec-Fetch-Site:
  none
  Sec-Fetch-User:
  ?1
  Sec-Gpc:
  1
  Upgrade-Insecure-Requests:
  1
  User-Agent:
  Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
  
  ```

可以看到请求头多出一个东西

+ ```http
  Cookie:
  MM_WX_NOTIFY_STATE=1; MM_WX_SOUND_STATE=1; JSESSIONID=C8D3160AB2F26FC1A9625F1595159138
  Host:
  localhost:8080
  
  ```

没错这就是Map集合里面的key，这个key被服务器传给浏览器记录了下来，我们再来看看响应头



响应头：

+ ```http
  Connection:
  keep-alive
  
  Content-Length:
  57
  Date:
  Mon, 18 Mar 2024 07:57:13 GMT
  Keep-Alive:
  timeout=20
  
  ```

这个时候是没有返回cookie了，不得不说这个创意着实是完美，另外，session是存在浏览器缓存里面的，浏览器关闭，cookie就没有了

这里有三个方法，各种域通用

+ ```java
  setAttrubute("","");
  getAttribute("", "");
  removeAttribute("", "");
  //底层是Map，一个key对应应该value，里面的value是对象
  ```

+ 