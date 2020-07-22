### 第一个vue代码：helloVue.js

1. 步骤

   - 创建`div`元素，给`div`设置`id`属性

   - 定义一个`Vue`实例对象，利用`el`属性将`div`挂载到实例对象上

   - 给`Vue`实例对象添加`data`数据

   - `data`里的数据就可以在`div`里显示（注意：只能在`div`里生效）

   - 这时，改变修改`Vue`实例里的数据，`div`里的数据也会跟着改变。

     

2. 代码

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
       <div id = "app">{{message}}</div>
       {{message}}  //此处，不会生效，必须在div标签内部
       <script>
           let app = new Vue({
           	//挂载元素
               el: '#app',
               //绑定数据
               data: {
                   message: 'helloVue'
               }
           })
   
       </script>
   </body>
   </html>
   ```

   