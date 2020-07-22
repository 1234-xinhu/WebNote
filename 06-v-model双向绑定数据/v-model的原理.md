### 1.v-model的基本使用

- 使用了v-model双向绑定数据后，当我们改变data里的数据时，视图区显示的值也会跟着改变
- 当我们在input中输入的值也会改变对应绑定变量值。

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
        <input type="text" v-model = "message">
        {{message}}
    </div>

    <script>
        let app = new Vue({
            el: '#app',
            data: {
                message: 'hello'
            }
        })
    </script>

</body>
</html>
```

### 2.v-model的原理

从上面的例子可知，所谓双向绑定可以分为两个步骤：

- 将data里的变量通过v-bind绑定到input的value上，这样就把变量的值给了input。

- 第二步给input添加一个input监听事件，当用户有输入的时候就及时把input的值给变量。

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
          <input type="text" :value = "message"  @input = "inputHandle">
          {{message}}
      </div>
  
      <script>
          let app = new Vue({
              el: '#app',
              data: {
                  message: 'hello'
              },
              methods:{
                  inputHandle(event){
                      this.message = event.target.value;
                  }
              }
          })
      </script>
  
  </body>
  </html>
  ```

  注意：怎么获取input的值呢

  inputHandle接受一个event对象，这个对象是默认传来的，通过它就可以获取input的值。