### v-bind动态绑定class(对象语法)

- 有时候我们期望对Dom元素的节点的class进行动态绑定，选择此Dom是否有指定class属性 

  - 步骤：

  1. 定义class类的样式，在style标签里写
  2. 给实例添加一个布尔型的变量，用来控制class类
  3.  在Dom元素中使用`:class={active:isActive}`，此时绑定的`class='active'`，isActive为true，active显示 
  4. 给按钮添加点击事件，控制Dom元素是否有`class='active'`的属性。 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <style>
        .active {
            color: pink;
        }
        .isline {
            font-size: 30px;
        }
    </style>
    <div id = "app">
       <p :class = "{active:isActive}">{{message}}</p>
       <button @click = 'change'>按钮</button>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
               isActive: true,
               message:'你好啊'
            },
            methods: {
                change(){
                    this.isActive = !this.isActive;
                }
            }
        })
    </script>
    
</body>
</html>
```

### v-bind动态绑定class(数组语法)

-  class属性中可以放数组，会依次解析成对应的class 
- 解析数组里的变量然后去实例里去匹配，给元素添加对应的class类

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <style>
        .active {
            color: pink;
        }
        .isline {
            font-size: 30px;
        }
    </style>
    <div id = "app">
        <!-- 不加单引号当成变量 -->
       <p :class = "[act,isl]">{{message}}</p>
       <!-- 加上单引号当成字符串 -->
       <p :class = "['act','isl']">{{message}}</p>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
               act: 'active',
               isl: "isline",
               message:'你好啊'
            }
        })
    </script>
    
</body>
</html>
```

注意：数组里的元素不能加单引号（因为加了单引号，就把他当做字符串，因为和类名不一致，找不到，就无法生效。）

效果如下：

![1595396258458](C:\Users\24023\AppData\Roaming\Typora\typora-user-images\1595396258458.png)

