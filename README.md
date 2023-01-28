# 모두가 볼 수 있고 참여할 수 있는 Digital Garden 만들기 🏡

[디지털 저장 창고 웹사이트 👈](https://juyoungdev.com)

## **Background**

> 5개월간 옵시디언을 활용하여 개발 지식을 습득해왔으나 다소 **폐쇄적이라는 제약 조건**으로 인해 공유가 어렵다는 문제를 만났습니다. 공유하지 않다 보니, 자연스럽게 글의 **퀄리티가 낮아졌다고 스스로 느꼈습니다**. 개념들 사이에 있는 상호 연결성을 찾는 시도는 좋았으나 피드백이 있다면 더 빠르게 배울 수 있지 않을까 생각했습니다. 위의 두 가지 문제를 해결하기 위해 나만의 웹사이트를 만들어 현재 내가 알고 있는 수준의 지식을 **공유**하고 댓글을 통해 개발자 준비생 혹은 현업 개발자분들의 issue 등록을 통해 **피드백**을 받아가며 모두에게 유의미한 지식 창고를 만들고 싶어 시작하게 되었습니다.

## 문제 해결 과정 💭

<details>
<summary>피드백을 받을 수 있으면 좋지 않을까?</summary>
<br>

**부연 설명** : 내가 쓴 글을 공유하는데 만족한다면 jekyll 오픈소스대로 사용하면 충분할 것 같습니다. 하지만 피드백을 받고 더 빠르게 지식을 습득하고 싶은 저의 열망으로 시작한 프로젝트이기에 만들어진대로 사용할 수 없었습니다.

- **정의** : 오픈소스의 코드를 사용하는데서 만족하지 않고 **뜯어봐야 한다**.

- **해결 과정** :

  1. 정적 웹사이트 생성 프레임 워크인 jekyll의 사이트 구조를 공식문서를 통해 파악하고 custom하여 사용.
  2. github issue의 위젯인 utteranc.es를 활용하여 댓글 기능 구현.
  3. 발생하는 에러 해당 오픈소스의 github issue에 질의를 통해 해결.

- **공부한 부분** : [jekyll](), [SSG](), [CSR](), [SSR]()
- **경험** : 루비로 만들어진 jekyll 프레임 워크를 사용해서 옵시디언의 그래프 및 지식 창고 개념을 그대로 구현할 수 있었다.

</details>

<details>
<summary>400개가 넘는 MD파일이 있는데 노트에 접근하는데 불편한 것 같은데?</summary>

<br>

**부연 설명** : 만민의 디지털 가든을 만든지 별로 되지 않았지만 제 옵시디언의 노트들을 조금씩 옮기다보니 벌써 약 400개가 넘는 md파일이 존재합니다. 400개의 노트들의 연결성을 제 웹페이지에서 보여주는데는 성공했지만 실질적으로 방문자에게 필요한 지식을 제공하는데 한계를 느꼈습니다.

- **정의** : 댓글 기능이 필수적이다.

- **해결 과정** :

  - **큰 문제를 해결하기 위한 작은 문제 해결 과정**
    <br>

  1. Algolia와 연동하는 과정에서 Index의 record가 10KB 초과 에러
     ![](https://velog.velcdn.com/images/sharphand1/post/52971534-1c18-4f8f-b7e7-4b2706fa79c8/image.png)
     [Algolia 연동했던 방법을 블로그를 활용하여 공유하였습니다.](https://velog.io/@sharphand1/Jekyll%EB%A7%8C%EB%AF%BC%EC%9D%98-%EB%94%94%EC%A7%80%ED%84%B8-%EC%B0%BD%EA%B3%A0-%EA%B2%80%EC%83%89-%EA%B8%B0%EB%8A%A5-%EB%A7%8C%EB%93%A4%EA%B8%B0)
     저의 웹페이지는 노트 간, 상호연결성을 보여줍니다. 그렇다보니 각 html의 데이터로 인해 10KB가 넘어가는 문제가 있었습니다. 이 문제를 해결하기 위해 현재 사용하고 있는 오픈소스의 코드를 분석해보니 그래프를 백링크를 만들어주는 plugIn의 File.write() 시스템 콜에 해당하는 코드를 삭제해주어 인덱스를 추가하는 과정에서는 그래프 데이터가 추가되지 않게 하였습니다.
     <br>

  2. 스크립트에 container : #searchBox가 읽히지 않는 문제

  ```
    error : Container must be `string` or `HTMLElement`. Unable to find #searchbox
  ```

  script를 id가 searchbox인 element 뒤에 실행시키면서 어렵지 않게 해결했으나 [critical-rendering-path](https://juyoungdev.com/critical-rendering-path)과 기본 script 속성을 복습할 수 있었습니다. 위의 에러는 script에서 불러오는 element보다 브라우저에서 먼저 실행돼, html element를 불러오지 못해서 생기는 문제였습니다. script 속성 중 async와 defer을 사용해서 해결하려고 했으나 head에 script가 담기면 디지털 가든이 아닌 모든 페이지에서 script가 실행되는 문제가 발생하여 단순하게 해결했습니다.
  <br>

  3. 검색창에 쿼리를 날리지 않아도 결과를 보여주는 문제

  ```js
  const search = instantsearch({
  	indexName: "digitalGarden",
  	searchClient,
  	searchFunction(helper) {
  		if (helper.state.query) {
  			helper.search();
  		}
  	},
  });

  const search = instantsearch({
  	indexName: "digitalGarden",
  	searchClient,
  	searchFunction(helper) {
  		const container = document.querySelector("#hits");
  		container.style.display = helper.state.query === "" ? "none" : "";
  		helper.search();
  	},
  });
  ```

  공식 문서를 찾아보니 instantSearch 모듈에 searchFunction 매소드를 통해 검색 행동을 제어할 수 있다고 합니다. 결과적으로 페이지가 로드 됐을때 자동 서치되는 것 방지한다고 합니다. 여기서 id가 hits인 돔요소에 접근하고 helper.state.query가 비어있으면 display:none으로 되도록 만들고 아니면 helper.search()하도록 로직을 만드니 해결했습니다.

  결과물
  ![](https://velog.velcdn.com/images/sharphand1/post/150a79c5-257a-4265-8047-6e01253213a5/image.gif)
  <br>

  4. 검색 기능 추가 이후, graph가 보이지 않는 문제
     추가전
     ![](https://velog.velcdn.com/images/sharphand1/post/140cace9-e5dd-47a8-9a68-ae7affe7a32b/image.png)
     검색 추가 후,
     ![](https://velog.velcdn.com/images/sharphand1/post/18e47156-3f5e-4bf6-aba1-72534c571d9e/image.png)

  **해결 과정**
  4-1. script가 읽히는 순서 재점검 (다양한 시도끝에 스크립트 문제는 아니라고 생각했습니다.)
  4-2. 검색 기능이 있는 script를 주석 처리하니 그래프가 보입니다. 그렇다면 검색 script와 graph script와 문제가 있는 것 같았습니다.
  4-3. {% include algolia.html %} 지킬의 liquid 문법을 공부하여 기본적으로 잘못 사용한것이 있는지 확인한 결과, 정상적으로 사용한 것을 확인했습니다.
  4-4. 그래프 script 와 algolia script 모두 cdn에서 가지고 오는데 여기서 생기는 오류인가?

- **공부한 부분** :algolia Doc

</details>

<details>
<summary>로컬 서버가 아닌 구글 검색을 통해 부모님께 웹사이트를 보여드리고 싶은데?</summary>

![](https://velog.velcdn.com/images/sharphand1/post/cd7391fd-ca5d-491e-aa04-1127adc5e9ac/image.png)

**부연 설명** : 부모님께서 어느날 아침, 제 디지털 지식 창고를 구경하고 싶어하셨습니다. 하지만 그 당시 제가 공부하는 공간에 컴퓨터를 놓고 오는 바람에 보여드릴 수가 없었습니다. 그때 제가 알기에 SSG가 SEO 측면에 유리하다고 알고 있었습니다. 그래서 구글에 검색해봤지만, 지식 창고와 연관된 제 벨로그와 인스타가 나왔습니다. 뭔가 잘못됐다는 것을 인지하고 journeyDev를 치면 제 디지털 지식 창고가 검색 결과로 나오게 하려 합니다.

- **정의** : Google Search Console에 등록하면 쉽게 해결되지 않을까.

- **해결 과정** :

  1. Jekyll SEO 라이브러리 이용
     -> 현재 사용하고 있는 오픈소스 내에 SEO를 최적화해주는 것을 발견하였습니다.
  2. 구글 검색 엔진에 등록
     google search console에 등록하려면 DNS record에 TXT 정보를 복사하여 붙혀넣어야합니다. 하지만 netlify로만 베포를했을때는 DNS 관리자 설정에 들어가면 사이트 이름밖에 수정할 수 없다는 것을 알게 됐습니다. 그래서 도메인을 구입합니다.
  3. 가비아를 통해 도메인 구매
  4. http인 사이트를 https로 변환
     netlify에서 무료로 제공해주고 있어 어렵지 않게 3일이 지나 변환이 되었으나 어떤 원리로 https 인증서를 발급해주는지 공부했습니다.

- **공부한 부분** : [DNS](https://juyoungdev.com/dns) , [https](https://juyoungdev.com/https) , [http](https://juyoungdev.com/http) [SEO](https://juyoungdev.com/seo)
- 경험 : 커스텀 도메인을 가비아를 통해 구입하고 netlify Name server DNS에 Google-Search-Console의 TXT의 정보를 넣어주어 구글 색인 봇이 크롤링을 할 수 있도록 했습니다.
</details>

## 페이지 구성

### home

![](/assets/id.png)
홈페이지로서 저에 대한 모든 정보들에 접근할 수 있는 페이지입니다.

### about

![](/assets/about.png)
현재 UI를 구상중에 있습니다.

### portFolio

최신순으로 진행했던 모든 프로젝트를 한 눈에 볼 수 있는 페이지입니다.

![](/assets/portFolio.png)

### digitalGarden

- 콘텐츠
  ![](/assets/digitalGarden.png)
- 댓글 참여
  ![](/assets/reply.png)
- 연관성 그래프 시각화
  ![](/assets/relation.png)

[오픈소스 README.md](https://github.com/maximevaillancourt/digital-garden-jekyll-template)

```

```
