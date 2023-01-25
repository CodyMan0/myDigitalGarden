---
---


출처 :
저자 :
URL : 
인용 : 

# 함수형 업데이트의 쓰임 (11.24)
- 함수형 업데이트 방식을 활용하여 의존성 배열에 state가 담기지 않도록 한것이 핵심!

```
  const onChange = useCallback(e => {
    const { name, value } = e.target;
    setInputs(inputs => ({
      ...inputs,
      [name]: value
    }));
  }, []);
```


# 이제 와서 알게 된것 (1.24)
- 위의 설명은 useCallback을 사용하여  맞지만 함수형 업데이트의 목적은  불변성을 유지시키기 위함이다. 리액트의 가상돔이 얕은 비교를 통해 상태가 변했는지를 알 수 있도록 하기 위해서!! 

### 생각의 연결고리
분야 :

키워드 :

관련있는 메모 : [[virtual-dom]] , [[react-immutability]]
