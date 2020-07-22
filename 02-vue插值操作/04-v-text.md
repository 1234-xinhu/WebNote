### v-text用法

- v-text 会覆盖dom元素中的数据 

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
          <h3>{{message}}  world</h3>
          <h4 v-text  = "message">world</h4>
      </div>
      <script src="../vue.js"></script>
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

  ![1595385998526](C:\Users\24023\AppData\Roaming\Typora\typora-user-images\1595385998526.png)

因为v-text会覆盖h4标签中`world`,所以显示结果为hello

总之，使用`{{message}}`是拼接变量和字符串，而是用v-text是直接覆盖字符串内容。 

