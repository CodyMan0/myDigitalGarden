---
---



Up : [[knowledge_MOCs]]

출처 :
저자 :
URL :https://youtu.be/tTFoClBZutw
인용 : 

알고리즘의 시간 복잡도를  계산할때 **최악의 경우**를 계산하는 방식 

# 시간 복잡도란
함수의 실행시간을 점근적 분석을 통해 점극적 표기번으로 표현하는 것을 말한다. 



```C
boolean exists(int[]inpus, int target) {
for (int i = 0; i < input.length; i++) {
	if(input[i] == target) {
	return true;
		}
	}
	return false;
}
```

시간 복잡도 구해보자. 
best는 0번째 존재 -> 오메가(1)
worst 마지막에 존재하거나 없을때 N번째 존재 -> O(n)

![[스크린샷 2023-01-14 오전 11.46.34.png]]


실행시간이란 함수 알고리즘 수행에 필요한 스텝 수 

-> n이 무한대로 가는 것을 표현 -> O(n)
: **점근적 분석**




### 생각의 연결고리
분야 :

키워드 :

관련있는 메모 :

