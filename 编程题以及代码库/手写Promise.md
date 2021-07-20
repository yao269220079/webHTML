# 手写 Promise

先看看 Promise 是怎么用的
解决回调地狱的问题
```js
new MyPromise((resolve, reject) => {
  setTimeout(() => {
    console.log("第一个 resolve");
    resolve(1);
  }, 1000);
})
  .then((res) => {
    // 返回一个Promise对象
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        console.log("第二个 resolve");
        resolve(res + 2);
      }, 2000);
    });
  })
  .then((res) => {
    console.log(res);
  });
```



