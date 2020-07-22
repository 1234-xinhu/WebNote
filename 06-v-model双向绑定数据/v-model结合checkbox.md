### v-model结合checkbox使用

 checkbox可以结合v-model做单选框，也可以多选框

1.代码

```html
    <div id = "app">
        <!-- 单选框 -->
        <div class="checjbox">
            <label for="agree">
                <input type="checkbox"  id = "agree" v-model = "isAgree">同意协议
            </label>
            <br>
            <button :disabled = "!isAgree">下一步</button>
        </div>
        <!-- 多选框 -->
        <div class="checkboxs">
            <label for="">
                <input type="checkbox" v-model = "hobby" value = "篮球">篮球
                <input type="checkbox" v-model = "hobby" value = "乒乓球">乒乓球
                <input type="checkbox" v-model = "hobby" value = "足球">足球
                <input type="checkbox" v-model = "hobby" value = "羽毛球">羽毛球
            </label>
            <p>我的爱好是：{{hobby}}</p>
        </div>
    </div>
    <script>
        let app = new Vue({
            el: '#app',
            data: {
                isAgree: false,
                hobby: []
            }
        })
    </script>

```

- checkbox结合v-model实现单选框时，先初始化一个变量为false,然后当选中时，变量变为true，然后用这个布尔值去控制按钮的禁用等。
- checkbox结合v-model实现多选框时，先初始化一个空数组， 用于存放爱好，将`hobbies`与checkbox对象双向绑定，此时选中，一个多选框，就多一个true，`hobbies`就添加一个对象。 

