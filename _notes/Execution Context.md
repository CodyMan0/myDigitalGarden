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


# 실행컨텍스트 

#한마디정리 


## 과정
1. 평가단계 
2. 실행단계 

var, 함수 선언문 먼저 


실행컨텍스트 
-> 호이스팅
-> 클로저 동작 방식
-> 테스크큐와 함께 동작하는 이벤트 헨들러와 비동기처리 
를 이해할 수 있게 된다 .

#한마디정리 실행컨텍스트는 4가지의 소스코드에 따라 다르다 

## 23.1 소스 코드(실행가능한 코드) 4가지
1. 전역 코드 
2. 함수 코드
	-> 지역 스코프 생성, 지역 변수 매개변수 arguments 객체를 관리
3. eval 코드 
4. 모듈 코드 


## 23.2 소스코드의 평가와 실행
평가과정 -> 선언문 제외하면 소스코드가 순차적 실행과정


## 23.3 실행 컨텍스트의 역할 
```js
const x = 1;
const y = 2;

//function 
function foo(a) {
	const x = 10;
	const y =2-;
console.log(a+x+y);
}

//함수호출

foo(100)

// 매서드 호출
console.log(x+y)
```

### 1. 전역 코드 평가 -> 실행 -> 함수 코드 평가 -> 실행 

#### 1. 전역 코드 평가
변수 선언문, 함수 선언문이 전역 스코프에 등록이 되고 var는 window 객체의 프로퍼티가 된다.

#### 2. 전역 코드 실행
평가가 끝나면 런타임 -> 코드 순차적으로 이때 값이 값이 할당되고 함수가 호출된다. 호출되면 전역 코드의 실행을 중단하고 {[[scheduling Policy]]과 비슷?} 실행 순서를 변경해서 내부로 들어간다

#### 3. 함수 코드 평가
매개 변수, 지역 변수 선언문이 먼저 평가되고 실행  -> 그 결과 생성된 변수가 지역 스코프에 지정 -> 함수 내부에서 쓰는 arguments 객체가 이때 생성되고 this 바인딩! 도 이떄 결정

#### 4. 함수 코드 실행
함수의 호출가 종료되면 이전 액션으로 돌아가야해서 스코프, 식별자, 코드 실행순서의 관리가 필요하다. 

---> 이 모든 것을 관리해주는게 **실행 컨텍스트**

즉. 실행컨텍스트는 소스코드를 실행하는데 필요한 식별자, 스코프, 코드의 실행순서 정보를 관리해주는 영역 


## 23.4 실행 컨텍스트 스택 

```js
const x = 1;

//function 
function foo() {
	const y =2;
	function bar () {
	const z =3
	console.log(x+y+z);
	}
bar();
}
foo(100); // 6
```

![[스크린샷 2022-12-27 오후 2.49.06.png]]











### 생각의 연결고리
분야 :

키워드 :

관련있는 메모 : [[const and let vs var ]]
