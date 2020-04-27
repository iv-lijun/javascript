[TOC]

# JavaScript 学习过程中的一些 Issue 记录



## 前言

为了辅助学习，在学习过程中遇到的各种 Issue 问题都将记录在此文档中，以便后期的回溯再理解。



## JavaScript 初级篇



### 1. 字符串参数

在学习 Vuex 时，官网的一个份示例代码中出现了<font color="red">“字符串参数”</font>的概念，代码片段如下：

```js
export default {
  name: "App",
  data () {
    return { localCount: 3 };
  },
  computed: mapState({
    count: state => state.count,
    // 上面箭头函数可换成如下写法，如果看的不是很理解的话：
    // count: function(state) {
    //   return state.count;
    // },
    // 或者：count() {},

    // 传字符串参数 'count' 等同于 `state => state.count`
    countAlias: "count",

    // 为了能够使用 `this` 获取局部状态，必须使用常规函数
    // 如果使用箭头函数, `this` 将指向全局对象 window
    countPlusLocalState(state) {
      return state.count + this.localCount;
    }
  })
};
```

**Issue**： `countAlias: "count"` 的取值竟然等于 `count` 这个变量值？原理是什么？

> 暂无回复

