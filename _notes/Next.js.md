---
---


---
aliases: []
tags : 
---
Up : [[HOME 🌎]]

출처 :
저자 :
URL : https://www.youtube.com/watch?v=ECMB4kUCKWQ&t=448s
인용 : 


#  흩날리는 개념 정리
1. server only file
-> _app.tsx , _document.tsx

2. 최초 실행은 _app.tsx (client에서 띄우길 바라는 전체 컴포넌트의 레이아웃)

3. 페이지 연산 담당 : useEffect를 활용한 데이터 패칭을 next.js는 서버에서 미리 처리할 수 있게 하는 것이  getInitialProps
-> 데이터 패칭을 서버에서 하면 속도가 빨라짐. 코드가 깔끔해짐.


4. ServerSide Cycle
```
1.  Next Server가 GET 요청을 받는다.
2.  요청에 맞는 Page를 찾는다.
3.  _app.js의 getInitialProps가 있다면 실행한다.
4.  Page Component의 getInitialProps가 있다면 실행한다. pageProps들을 받아온다.
5.  _document.js의 getInitialProps가 있다면 실행한다. pageProps들을 받아온다.
6.  모든 props들을 구성하고, _app.js > page Component 순서로 rendering.
7.  모든 Content를 구성하고 _document.js를 실행하여 html 형태로 출력한다.
```


5. nextPage는 페이지에 붙혀주는건가??? 



react + express.js + react-router-dome + serverSide-rendering

-> 모든 애들의 개념을 내재화해서 쉽게 사용할 수 있다.


넥스트는 자동으로 번들 사이즈를 GGB로 압축해준다.

[[next.Image]]


6. [[next page]]
6-1. [[getStaticProps]]
6-2. [[getServerSideProps]] 오늘 이해한다 (1.10)
6-3. [[next_seo]]






### 생각의 연결고리
분야 : [[difference framework and library]]

키워드 :

관련있는 메모 :
