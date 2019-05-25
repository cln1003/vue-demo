# gshop

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

点击input的时候，把数据传递到运行文件中（v-modul双向数据绑定，input改变数据就改变），通过store库读取删除，更改内存中的值
一开始就要读取get保存的数据，然后再更新数据，再把保存的数据遍历到历史记录中的ul中
点击垃圾箱就删除历史记录
