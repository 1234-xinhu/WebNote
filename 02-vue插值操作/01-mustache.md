### Mustache语法

- mustache是胡须的意思，因为`{{}}`像胡须，又叫大括号语法。 
- mustache用于将vue实例中的`data`中的数据渲染到页面上
- mustache语法不仅可以直接写变量，还可以写表达式
- `{{ }}`是最常用的插值语法

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
        {{firstname + '  ' + lastname}}
        {{firstname}}  {{lastname}}
        <p>{{message * 2}}</p>
    </div>
    <!-- mustache语法不仅可以直接写变量，还可以写表达式 -->
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                message: 100,
                firstname: 'tx',
                lastname: 'z'
            }
        })
    </script>
</body>
</html>
```

