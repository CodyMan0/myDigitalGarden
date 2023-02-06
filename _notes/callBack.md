---
---

정의 : 함수에 파라미터로 들어가는 함수
용도 : 순차적으로 실행하고 싶을때 씀



```js
/* callback */

function add10(a, callback){

setTimeout(() => callback(a + 10), 100);

}

​

add10(5, res => {

console.log(res); // 15

});
```

- promise 

```js
function add20(a){

return new Promise(resolve => setTimeout(() => resolve(a + 20), 100));

}

​

add20(5).then(console.log); // 25
```