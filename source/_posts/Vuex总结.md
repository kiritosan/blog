---
title: Vuex总结
date: 2021-12-08 21:51:23
tags:
---
Vuex作用:状态管理 管理数据

通过新建store文件夹,然后在里面新建index.js 导入vue和Vuex,然后new store并导出。

接着在main.js里面导入store,然后就可以使用this.&store来使用Vuex了。

new store过程中需要传入配置项：states（储存数据），mutations（修改state），actions（异步操作），getters（类似computed）

数据统一存储到states里面，states里面的出不能直接修改，想要修改时通过mutations来修改，mutations里面储存修改states的方法，调用其中方法可以通过this.&store.commit(方法名)，也可以通过在methods里mapMutations。

但是在mutations里面的方法不能执行异步操作，执行之后vue调试工具检测不到states的变化，虽然实际页面的值改变了。

想要异步操作的时候在actions里面写异步方法，在这个方法中通过commit来触发mutaions里的方法来修改数据，而actions里面的方法则需要通过dispatch来调用。

有各种映射函数在简化代码。
mapStates this.&store.state.状态名
mapMutations this.&store.commit(方法名)
mapActions this.&store.dispatch(方法名)
mapGetters this.&store.getters.状态名


