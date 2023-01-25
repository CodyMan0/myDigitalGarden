---
---

1. **다른 객체 바탕으로 만들어진 객체**
	자신의 원형 객체를 `__proto__`링크를 자동으로 가지게 된다.
2. **함수 객체일 경우**
	proto외에 함수의 Prototype 객체가 자동으로 만들어지고 Prototype 객체의 constructor를 통해 Person을 가르키고 Person은 프로토타입 속성으로 프로토 타입 객체를 가르켜 순환 참조가 이뤄진다. 
	![[스크린샷 2022-12-17 오후 12.28.12.png]]
3. **new 연산자와 함수로 만들어진 객체**
	여기의 차이점은 함수의 프로토타입 객체 안에 `__proto__`링크를 자동으로 삽입한다는 것.

-> 영준님 설명 추가 