1. [第 6 题：请分别用深度优先思想和广度优先思想实现一个拷贝函数？](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/10)

2. async/await

```
let a = 0
let b = async () => {
  a = a + await 10
  console.log('2', a) // -> '2' 10
}
b()
a++
console.log('1', a) // -> '1' 1
```

- 首先函数 b 先执行，在执行到 await 10 之前变量 a 还是 0，因为 await 内部实现了 generator ，generator 会保留堆栈中东西，所以这时候 a = 0 被保存了下来
- 因为 await 是异步操作，后来的表达式不返回 Promise 的话，就会包装成 Promise.reslove(返回值)，然后会去执行函数外的同步代码
- 同步代码执行完毕后开始执行异步代码，将保存下来的值拿出来使用，这时候 a = 0 + 10

3. 三次握手，四次挥手

- https://juejin.cn/post/6844903731704791054

- https://zhuanlan.zhihu.com/p/53374516


4. setState原理

https://github.com/sisterAn/blog/issues/26

5. 原型，class ,es5/6

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/20

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/23

有个instanceof原型的题，记不清了，实现instanceof ?

6. 重绘、回流

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/24

7. 发布，订阅

https://www.cnblogs.com/onepixel/p/10806891.html

https://juejin.cn/post/6978728619782701087

8. event loop

https://juejin.cn/post/6844903761949753352

9. 模块化

https://www.processon.com/view/link/5c8409bbe4b02b2ce492286a#map

https://www.cnblogs.com/ailsa-qin/p/8494219.html

https://segmentfault.com/a/1190000023078400

好文章： https://zhuanlan.zhihu.com/p/113009496

10. token cookie csrf xss

<img width="936" alt="image" src="https://user-images.githubusercontent.com/34086399/156313683-f97141eb-f1d9-4d98-9c91-c1b5d44b7f99.png">

同源策略：
- https://www.ruanyifeng.com/blog/2016/04/same-origin-policy.html
- https://www.ruanyifeng.com/blog/2016/04/cors.html


11. 聊聊 Vue 的双向数据绑定，VUE原理解析

todo

12. 各种状态管理redux, vuex , mobox

https://zhuanlan.zhihu.com/p/53599723

13. Virtual DOM 真的比操作原生 DOM 快吗？谈谈你的想法

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/47

14. 浏览器缓存

https://www.jianshu.com/p/54cc04190252

15. 实现flatten函数

迭代的实现:

```
let arr = [1, 2, [3, 4, 5, [6, 7], 8], 9, 10, [11, [12, 13]]]

const flatten = function (arr) {
    while (arr.some(item => Array.isArray(item))) {
        arr = [].concat(...arr)
    }
    return arr
}

console.log(flatten(arr))
```
递归的实现(ES6简写):
```
const flatten = array => array.reduce((acc, cur) => (Array.isArray(cur) ? [...acc, ...flatten(cur)] : [...acc, cur]), [])
```

16. BFC

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/59#issue-424008233

https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/59#issuecomment-475518785