### v-html

-  在某些时候我们不希望直接输出`[百度一下](http://www.baidu.com)`这样的字符串，而输出被html自己转化的超链接。此时可以使用v-html。 

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
        <p>不使用v-html:</p>
        <h3>{{url}}</h3>
        <p>使用v-html:</p>
        <h3 v-html = "url">{{url}}</h3>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                url:'<a href = https://www.bilibili.com/video/BV15741177Eh?p=13>哔哩哔哩</a>'
            }
        })
    </script>
</body>
</html>
```

![1595385366818](C:\Users\24023\AppData\Roaming\Typora\typora-user-images\1595385366818.png)

