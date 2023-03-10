---
---

## **✏ 객체를 만드는 방법**

생성자 함수도, 클래스도 결국에는 **객체를 만드는 방법**이다. 그래서 가장 먼저 자바스크립트에서 객체를 만드는 방법에 대해서 정리해 보고자 한다.

### **1) 객체 리터럴**

객체 리터럴은 가장 쉽게 객체를 만드는 방법으로 `{}`로 내부에 넣을 속성과 메소드를 담아 만들 수 있다.

```
const position={
    x:1,
    y:2,
}
```

### **2) 생성자 함수**

생성자 함수는 new연산자를 이용해 객체, 인스턴스를 생성하는 함수를 의미한다. 객체 리터럴보다는 상대적으로 복잡하게 객체를 만드는 방법이다.

### **2-1) Object 생성자 함수**

Object 생성자 함수와 new 키워드를 이용하면 빈 객체를 생성한다. 이후에 객체를 만들고 내부에 속성과 메소드를 추가할 수 있다.

```
const person = new Object();

person.name = `lee`;
person.sayHello = function () {
  console.log(this.name);
};
```

Object 생성자 함수 외에 빌트인 객체들도 new와 함께 생성할 수 있다.

```
const strObj = new String('youngjun');
console.log(strObj);

const numObj = new Number(123);
console.log(numObj);

const boolObj = new Boolean(true);
console.log(boolObj);

const func = new Function('x', 'return x*x');
console.log(func);

const arr = new Array(1, 2, 3);
console.log(arr);

const regExp = new RegExp(/ab+c/i);
console.log(regExp);

```

### **2-2) 사용자 정의 생성자 함수**

함수 내부에 인스턴스에 추가할 속성과 메소드를 정의한 후에 new 키워드로 인스턴스를 만들 수 있다.

```
function Person(name) {
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
}
const person = new Person('youngjun');
console.log(person);

```

### **3) Object.create()**

[[Prototype]]의 상속을 이용해 객체를 만드는 방법으로 자체적으로는 빈 객체를 만들지만, prototype으로 전달 받은 속성과 메소드를 사용할 수 있다.

```
const obj1 = { a: 1, b: 2 };
const obj2 = Object.create(obj1);

console.log(obj2); // {}
console.log(obj2.a); // 1
```

## **😁 생성자 함수의 필요성과 동작방식**

객체를 만드는 방법들 중에 왜 생성자 함수가 쓰이는지와 동작 방식을 알아보자.

### **생성자 함수의 필요성**

위의 세가지 방식 중 객체 리터럴이 가장 편하게 객체를 만들 수 있는 방법이다. 객체에 필요한 값을 직접 정의해줄 수 있어 커스텀하기도 쉽다. 하지만 **똑같은 속성과 메소드를 가지는 여러개의 객체**가 필요하다면 객체 리터럴로 일일이 만드는 것은 비효율적이다.

```
const person1 = {
  name: "youngjun",
  sayHello() {
    console.log(this.name);
  }
}

const person2 = {
  name: "minjae",
  sayHello() {
    console.log(this.name);
  }
}
```

이렇게 여러 개의 유사한 객체가 필요할 때, **템플릿을 만들고 필요한 부분만 주입받아서 사용하면 편하지 않을까**라는 생각이 든다. 이럴 때 사용할 수 있는 것이 바로 생성자 함수다.

```
function Person(name) {
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
}
const person = new Person('youngjun');
console.log(person);

```

### **동작방식**

생성자 함수를 이용해 객체를 만들 때 **1) 인스턴스생성 2) 인스턴스 초기화 3) 인스턴스 반환** 세 가지 과정으로 진행된다. 위의 예제를 다시 살펴보자.

```
function Person(name) {
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
}
const person = new Person('youngjun');
console.log(person)
```

### **1) 인스턴스 생성**

생성자 함수는 암묵적으로 빈 객체를 생성하고, 생성자 함수의 [[this-binding]]이 된다.

```
function Person(name) {
    // 1) 인스턴스 생성, this와 바인딩
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
}
const person = new Person('youngjun');
console.log(person)
```

### **2) 인스턴스 초기화**

this에 바인딩 되어있기 때문에 이후에 this를 이용해 초기화 과정을 진행할 수 있다.

```
function Person(name) {
    // 1) 인스턴스 생성, this와 바인딩
    // 2) 인스턴스 초기화
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
}
const person = new Person('youngjun');
console.log(person)
```

### **3) 인스턴스 반환**

초기화 과정이 끝나면 **return으로 적지 않아도 암묵적으로 this가 반환**된다. 이때 다른 객체를 return하면 명시한 객체가 반환되고, 원시값으로 반환하면 암묵적으로 this가 반환된다.

```
function Person(name) {
    // 1) 인스턴스 생성, this와 바인딩
    // 2) 인스턴스 초기화
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
   // 3) 인스턴스 반환
}

// 명시적으로 다른 객체 반환
function Person(name) {
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
  return {};
}
const person = new Person('youngjun');
console.log(person); // {}

//명시적으로 원시값 반환
function Person(name) {
  this.name = name;
  this.sayHello = function () {
    console.log(this.name);
  };
  return 'hi';
}
const person = new Person('youngjun');
console.log(person); // Person { name: 'youngjun', sayHello: [Function (anonymous)] }
```

## **⛏ 내부 메소드**

생성자 함수는 일반함수와 동일하게 작성했지만 다르게 동작하는 것처럼 보인다. 어떤 차이가 있는지 생성자 함수의 내부 동작을 캐보자.

### **함수 객체의 [[call]]과 [[Construct]]**

함수는 객체다. 객체이기 때문에 기존에 우리가 사용하던 객체의 특성을 이용할 수 있다.

```
function bar() {}
bar.a = 1;
console.log(bar.a); // 1
```

하지만 함수 객체는 일반 객체와 다르게 호출할 수 있고 생성자 함수로도 작동할 수 있다. 그이유는 함수 객체에는 일반 객체의 내부 메소드뿐만 아니라 **[[call]]과 [[construct]]**가 있기 때문이다. 이때 중요한 부분은 모든 함수는 [[call]]을 가지고 있어 호출이 가능하지만, `모든 함수가 [[construct]]를 가지는 것은 아니다`라는 것이다. 이렇게 [[construct]]를 가지는 함수를 constructor라고 부르고 [[construct]]를 가지지 않는 함수는 non-constructor라고 부르며 다음과 같이 정리된다.

-   constructor: 함수 선언문, 함수 표현식, 클래스
-   non-constructor: 메소드 축약, 화살표 함수

이렇게 내부적으로 [[construct]]를 가지고 있다면 new와 함께 사용하면 언제든 생성자 함수로 작동할 수 있다. 그렇기 때문에 생성자 함수로 사용하지 않을 거라면 화살표함수와 객체 내부에서는 메소드 축약을 사용하는 게 더 좋다고 생각된다.

```
// 일반함수를 생성자함수로
function add(x, y) {
  return x + y;
}

let inst = new add();
console.log(inst); //add{}

function createUser(name, role) {
  return { name, role };
}

inst = new createUser('lee', 'admin');
console.log(inst);// { name: 'lee', role: 'admin' }

//생성자함수를 일반함수로
function Circle(radius) {
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

const circle = Circle(5);
console.log(circle); // undefined
console.log(radius); // 5
console.log(getDiameter()); //10
```

위 코드에서 일반함수를 생성자함수로 사용할 수 있는 것을 볼 수 있고, 생성자 함수를 일반 함수로 사용하는 경우에서는 this가 window가 되어 전역객체의 속성과 메소드로 등록된 것을 볼 수 있다.

## **🎚 생성자 함수 구분**

위의 코드처럼 일반함수와 생성자함수는 구분하기 힘들기 때문에, 생성자 함수는 `대문자로 시작하는 Pascal표기법`을 이용한다. 하지만 이걸로도 구분하기 어렵기 때문에 `new.target`을 이용해 new를 이용해 생성자 함수로 함수가 호출되었는지 확인할 수 있다.

new.target은 new연산자와 함께 호출되면 함수 자신을 가리키고, 일반함수로 호출되었을 때는 undefined로 나타나기 때문에 각각에 따른 처리가 가능하다.

```
function Circle(radius) {
  if (!new.target) {
    return new Circle(radius);
  }
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

const circle = Circle(5);
console.log(circle.getDiameter());

```

위 코드에서 new 키워드 없이 호출되었지만 new.target을 이용해 생성자함수로 다시 호출시켜 객체를 만든 것을 볼 수 있다.