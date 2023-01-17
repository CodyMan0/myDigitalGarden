---
---


---
aliases: []
tags : 
---
Up : [[HOME 🌎]]

출처 :
저자 :
URL : 
인용 : 

자바스크립트 동작을 느리게 하는 코드를 말하는 것 같다. 

무거운 코드가 스텍에 있을때 큐 영역으로 부터 받지 못하는 상황을 의미.

자바스크립트의 동기적 특성때문에 브라우저[[Web API]]는 Ajax 요청을 비동기적으로 실행한다.


setTimeout과 동일한 동작을 하는 함수를 만들었을때

```js
function sleep(func, delay) {

const delayUntil = Date.now() + delay;

  

while (Date.now() < delayUntil) func();

}

  

function foo() {

console.log("foo");

}

  

function bar() {

console.log("bar");

}

  

sleep(foo, 3 * 1000);

  

bar();
```
![[스크린샷 2022-12-31 오전 11.28.14.png]]

# 블로킹 한계 극복
비동기 콜백으로 싱글 스레드의 한계를 극복할 수 있다. 






### 생각의 연결고리
분야 :

키워드 :

관련있는 메모 : [[AJAX]],[[Non-blocking]]

