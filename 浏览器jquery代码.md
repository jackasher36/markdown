# 浏览器jquery代码

```javascript
// 引入jQuery
var script = document.createElement('script');
script.src = 'https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js';
document.head.appendChild(script);

// 等待jQuery加载完成后执行代码
script.onload = function() {
    // 使用jQuery选择器遍历元素并输出索引到控制台
    jQuery(".user-info .user-name").each(function(index, item) {
        console.log(index);
    });
};

```

