### computed和methods的区别

- computed
  - computed里的计算属性具有缓存性，会监听data数据变化
  - 只有当数据发生了变化时，才会重新计算
  - 所以当数据量大时，使用computed性能更优化

- methods
  - 无论数据变不变，每次重新加载都会再次调用

