### v-pre的用法

- 有时候我们希望mustache语法中的变量不被解析，而是保留原样，就可以使用v-pre

```html
    <div id = "app">
        <p>使用v-pre前：</p>
        <h3>{{message}}</h3>
        <p>使用v-pre后：</p>
        <h3 v-pre = 'url'>{{message}}</h3>
        <!-- 保留，不被解析 -->
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                message:'hello world'
            }
        })
    </script>
```

![1595386589291](C:\Users\24023\AppData\Roaming\Typora\typora-user-images\1595386589291.png)