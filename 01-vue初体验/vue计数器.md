### Vue案例：计数器

- 利用vue实现一个简易计数器，当按下`+`按钮时，计数器+1，按下`-`按钮时，计数器-1

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
  </head>
  <body>
      <div id="app">
          <h3>当前计数：{{count}}</h3>
          <button @click= "add">+</button>
          <button @click = "sub">-</button>
      </div>
      <script src="../vue.js"></script>
      <script>
          const app = new Vue({
              el: '#app',
              data: {
                  count: 0
              },
              methods:{
                  add(){
                      console.log("add");
                      this.count++
                  },
                  sub(){
                      console.log("sub");
                      this.count--
                  }
              }
          })
      </script>
  </body>
  </html>
  ```

  注意：1.  `@click`为语法糖简写形式，完整为`v-on:click`

  ​			2. `methods`里的方法也为语法糖简写形式。

1. 创建vue对象实例并初始化一个变量count = 0
2. 在vue对象实例定义两个方法，`add()`,`sub()`,并给两个button按钮添加点击事件
3. 当用户点击按钮时，会自动调用添加的事件`add()`,`sub()`

