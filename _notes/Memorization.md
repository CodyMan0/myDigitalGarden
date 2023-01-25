---
---


- 리액트 최적화의 기본 사항
 ==state가 변하면 해당 컴포넌트를 포함한 하위 컴포넌트들은 모두 리렌더링 된다.==
 
Memoization은 특정한 값을 저장해뒀다가, 이후에 해당 값이 필요할 때 새롭게 계산해서 사용하는게 아니라 저장해둔 값을 활용하는 테크닉을 의미.

함수 컴포넌트는 근본적으로 함수입니다. 그리고 리액트는 매 렌더링마다 함수 컴포넌트를 다시 호출합니다. 함수는 기본적으로 이전 호출과 새로운 호출간에 값을 공유할 수 없습니다. 만약 특정한 함수 호출 내에서 만들어진 변수를 다음 함수 호출에도 사용하고 싶다면 그 값을 함수 외부의 특정한 공간에 저장해뒀다가 다음 호출 때 명시적으로 다시 꺼내와야 하는데 너무 복잡합니다. 그래서 리액트에서는 함수 컴포넌트에서 값을 memoization 할 수 있도록 API를 제공해주고 있습니다.

# APIs
[[React.memo]]

값을 memorization : [[useMemo]]

사용하기 더욱 쉽게 만든 : [[useCallback]]