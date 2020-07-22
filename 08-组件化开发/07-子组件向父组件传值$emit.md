### 1.子组件向父组件传值

1.在子组件中定义一个方法`btnClick(item)`，使用`$emit`，'itemclick'是自定义的事件名，`item`是传过去的值。

```javascript
      methods: {
        btnClick(item) {
          //itemclick为自定义的事件
          this.$emit('itemclick', item)
        }
      },
```

2.在子组件中监听点击事件并回调此方法

```html
<div>
      <button v-for="(item, index) in categoties" :key="index" @click="btnClick(item)">              {{item.name}}
      </button>
</div>
```

3.在父组件中定义一个方法cpnClick(item)

```javascript
methods: {
	cpnClick(item) {
		console.log('cpnClick'+item.name);
	}
},
```

4.并在父组件（vue实例）中调用 `<cpn @itemclick="cpnClcik"></cpn>` , 父组件监听事件名为 ` itemclick `的子组件传过来的事件。

```html
<cpn @itemclick="cpnClick"></cpn>
```

总代码

```html
 <!-- 父组件 -->
  <div id="app">
    <!-- 不写参数默认传递btnClick的item -->
    <cpn @itemclick="cpnClick"></cpn>
  </div>

  <!-- 子组件 -->
  <template id="cpn">
    <div>
      <button v-for="(item, index) in categoties" :key="index" @click="btnClick(item)">             {{item.name}}
      </button>
    </div>
  </template>

  <script src="../vue.js"></script>

  <script>
    const cpn = {
      template: "#cpn",
      data() {
        return {
          categoties: [{
              id: 'aaa',
              name: '热门推荐'
            },
            {
              id: 'bbb',
              name: '手机数码'
            },
            {
              id: 'ccc',
              name: '家用家电'
            },
            {
              id: 'ddd',
              name: '电脑办公'
            },
          ]
        }
      },
      methods: {
        btnClick(item) {
          this.$emit('itemclick', item)
        }
      },
    };
    const app = new Vue({
      el: "#app",
      data() {
        return {

        }
      },
      methods: {
        cpnClick(item) {
          console.log('cpnClick'+item.name);
        }
      },
      components: {
        cpn
      },
    })
  </script>
```

