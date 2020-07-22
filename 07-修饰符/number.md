- number 可以让输入的内容自动转成数字类型
- 因为我们在默认情况下，无论我们在输入框输入字符串还是数字，都会当成字符串进行处理。

```html
    <div id = "app">
        <input type="number" v-model.number = "message">
        {{typeof message}}//number
    </div>

```

