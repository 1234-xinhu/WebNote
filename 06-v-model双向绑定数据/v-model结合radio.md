```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="../vue.js"></script>
</head>
<body>
    
    <div id = "app">
        <label for="male">
            <input type="radio" id = "male" name = "sex" value = "男" v-model = "sex">男 
        </label>
        <label for="female">
            <input type="radio" id = "female" name = "sex" value = "女" v-model = "sex">女
        </label>
        <p>您选择的性别是： {{sex}}</p>
    </div>

    <script>
        let app = new Vue({
            el: '#app',
            data: {
                sex: ' '
            }
        })
    </script>

</body>
</html>
```

通过v-model绑定sex变量，然后渲染到页面中。