### v-once 的用法

- v-once表示dom元素只会被渲染一次，当元素修改时，不会被重新渲染

- 所以v-once不常用于开发中，只有当防止别人修改时，可以用v-once

  ```html
      <div id = "app">
          <h2>{{message}}</h2>
          <h3 v-once>{{message}}</h3>
          <!-- v-once 指令的数据不能被改变 -->
      </div>
      <script src="../vue.js"></script>
      <script>
          let app = new Vue({
              el: '#app',
              data: {
                  message: 100
              }
          })
      </script>
  
  ```

  - 当message值发生改变时，只有h2标签里的值会改变，h3标签里值还是100

