# 计算属性的setter和getter

- 在计算属性中有两个方法，setter和getter

- 但一般在计算中，都不会用到setter，也就是说，这时计算属性的属性都是只读的

- 当然也可以使用setter修改,当被修改时，会自动调用setter()

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
        <p>{{fullName}}</p>
        <!-- fullName 是一个属性，不是方法，不需要加（） -->
    </div>
    <script src="../vue.js"></script>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                firstname: 'z',
                lastname: 'tx'
            },
            computed:{
               fullName: {
                   //一般没有set方法，计算属性为只读属性
                   //该方法自动调用
                    set: function(newName){
                       let names = newName.split(' ');
                       this.firstname = names[0];
                       this.lastname = names[1];
                    },
                    get: function(){
                        return this.firstname + ' ' + this.lastname
                    }
               }
            }
        })
    </script>
</body>
</html>
```

