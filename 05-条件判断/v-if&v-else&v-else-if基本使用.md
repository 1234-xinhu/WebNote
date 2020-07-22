# 1. v-if、v-else、v-else-if

1. v-if

   - 只有当条件成立时才会执行，条件为false时，不会创建DOM元素

2. v-else

   - 与v-if结合使用，当v-if条件不成立时，才会执行

     

```javascript
<div v-if = "grade < 60">成绩不及格</div>
<div v-else if = "grade < 90">成绩良好</div>
<div v-else>优秀</div>
```

# 2. v-if、v-else小案例

 功能：在登录网站是经常可以选择使用账户名或者邮箱登录的切换按钮。要求点击按钮切换登录方式。 

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
        <span v-if = "istrue" class="username">
            <label for="username">用户名登录:</label>
            <input type="text" id = "username" placeholder="用户名登录" key = "username">
        </span>
        <span v-else class="email">
            <label for="email">邮箱登录:</label>
            <input type="text" id = "email" placeholder="邮箱登录" key ="email">  
        </span>
        <button @click = 'isChange()'>切换</button>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                istrue:  true
            },
            methods:{
                isChange(){
                    this.istrue = ! this.istrue;
                }
            }
        })
    </script>
    
</body>
</html>
```

这里需要注意：如果已经输入了账号了，此时想切换到邮箱输入，输入框未自己清空。 

所以解决办法是:给input输入框加key属性，避免浏览器的就地复用策略。

key值作用： 为了更高效地更新虚拟dom.