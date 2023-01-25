---
---



setTimeout을 사용하면 
```js
function foo() {

console.log("foo");

}

  

function bar() {

console.log("bar");

}

setTimeout(foo, 3 * 1000);
bar();


  

bar();
```

![[스크린샷 2022-12-31 오전 11.29.14.png]]


### 관련있는 메모
[[asychonous]]