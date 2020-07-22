### v-bind动态绑定style(对象语法)



```html
    <div id = "app">
       <p :style = "{fontSize: fontsize}">我是p</p>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
               fontsize: '60px'
            }
        })
    </script>

```

注意：fontsize不能加单引号或双引号，为一个变量

## v-bind动态绑定style(数组语法)

```html
       <p :style = "{fontSize: fontsize}">我是p</p>
       <p :style= "[styleArr]">我也是p</p>
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                fontsize: '60px',
                styleArr: {
                    backgroundColor: "pink"
                }
            }
        })
    </script>

```

