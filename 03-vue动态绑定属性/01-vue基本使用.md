### v-bind的基本使用

- 我们可以给一些标签的动态绑定属性值，当数据发生改变 时，浏览器会响应式的加载资源。

   如`img`的`src`属性，超链接`a`的`href`属性

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id = "app">
       <img :src="url" alt="">
       <br>
       <a :href="href">百度一下</a>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                url:'https://talent.baidu.com/external/baidu/images/header/12cm.jpg',
                href: "http://www.baidu.com"
            }
        })
    </script>
    
</body>
</html>
```

- 当我们把修改url,href值时，浏览器会加载对应的图片和超链接。

  