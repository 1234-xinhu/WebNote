### 1.父组件给子组件传递数据

#### 1.1 使用props属性，父组件给子组件传递数据

 使用组件的`props`属性 

```javascript
       const cpn = {
            template: "#cpn",
            props: {
                cperson:{
                    type: Object,
                    default(){
                        return {}
                    }
                }
            }
        }

```

 向cmessage对象传值 

```html
   <div id = "app" >
        <cpn :cperson = "person"></cpn>
        <!-- v-bind不识别驼峰命名，所以不能写成cPerson -->
    </div>
    <template id = "cpn"> 
        <div>
            {{cperson}}
        </div>
    </template>

```

```javascript
        let app = new Vue({
            el: '#app',
            data: {
                person:{
                    name: "ztx",
                    age: 18
                }
            },
            //注册局部组件
            //注册子组件cpn
            components: {
                cpn
            }
        })
```

父组件向子组件cpn传递了一个对象{name: "ztx",age:18}

#### 1.2 props属性使用

> 数组写法

```javascript
props: ['cmovies', 'cmessage']
```

> 对象写法

```javascript
  props: { 
          cmessage: {
              type: String,
              default: 'zzzzz'
          }
  }
```

> props属性的类型限制

```javascript
//1.类型限制(多个类使用数组)
cmovies:Array,//限制为数组类型
cmessage:String,//限制为Strin类型
cmessage:['String','Number']//限制为String或Number类型
```

> props属性的默认值

```javascript
// 提供一些默认值
        cmessage: {
              type: String,
              default: 'zzzzz',//默认值
        }
```

> props属性的必传值

```javascript
cmessage: {
          type: String,
          default: 'zzzzz',
          required: true //在使用组件必传值
        }
```

> 类型是Object/Array，默认值必须是一个**函数**

```javascript
//类型是Object/Array，默认值必须是一个函数
cmovies: {
	type: Array,
	default () {
		return [1, 2, 3, 4]
	}
},
```