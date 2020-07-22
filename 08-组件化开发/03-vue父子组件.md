### vue父子组件

---



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
        <cpn2></cpn2>
    </div>

    <script>
        const cpnC1 = Vue.extend({
            template: `
               <div>
                    <h3>我是标题</h3>
                    <p>我是内容</p>
                    <p>我是内容</p>
               </div>
            `
            })
        const cpnC2 = Vue.extend({
            template: `
               <div>
                    <h3>我是标题</h3>
                    <p>我是内容</p>
                    <p>我是内容</p>
                    <cpn1></cpn1>
               </div>
            `,
            //注册子组件cpn1
            components: {
                cpn1:cpnC1
            }
        })
         
        let app = new Vue({
            el: '#app',
            data: {
                message: 'hello99'
            },
            //注册子组件cpn2
            components: {
                cpn2:cpnC2
            }
        })
    </script>

</body>
</html>
```

上面cpn1在cpn2中注册，并且在template模板中使用了组件cpn1，则cpn1就是cpn2的子组件。

而cpn2又在vue实例中注册，并且在div实例对象中使用，则cpn2时vue实例的子组件。

 <u>注意：组件就是一个vue实例，vue实例的属性，组件也可以有，例如data、methods、computed等</u>。 

