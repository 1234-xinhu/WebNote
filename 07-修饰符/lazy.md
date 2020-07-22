- `lazy`修饰符可以让数据失去焦点或回车时才更新数据。

```html
<div id = "app">
        <input type="text" v-model.lazy = "message">
        {{message}}
    </div>
```

