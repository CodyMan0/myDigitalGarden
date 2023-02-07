---
layout: page
title: About
permalink: /about
---

<div id="introContainer">
  <div class='introduction'>
    <h1 class="skillSetTitle">BACKGROUND 😀</h1>
    <p>안녕하세요. 서울 광진구에 거주하고 있는 프론트엔드 개발자 이주영입니다.<br>저는 영문학을 전공으로 하였습니다.하지만 우연치않게 프로그래밍 입문이라는 교양 수업을 듣고 프로그래밍에 대해 관심을 가지게 되었습니다.
    <br>
    theOdinProject이라는 오픈소스를 활용하여 3개월간 <strong>독학</strong>을 하였고 이후 팀프로젝트 경험을 위해 <strong>부트캠프</strong>를 진행하면서 개발자의 역량을 키우는데 노력했습니다. 그 후 한달간 원티드 프리온보딩 코스를 통해 새로운 기술을 사용해보며 다양하게 학습하였습니다. 그 동안 배웠던 것들을 정리하며 챌린징한 상황을 맞이할 준비를 하고 있습니다.
    </p>
  </div>
  <div class='introduction'>
    <h1 class="skillSetTitle">KNOW WHO I'M  🌱</h1>
    <ul>
    <li> 전 주변 사람들에게 <strong>에너지</strong>를 주는 사람입니다. </li>
    <li> 전 <strong>공감력이</strong> 뛰어나 <strong>협업 능력</strong>이 뛰어난 사람입니다. </li>
    <li> 전 <strong>밝고 긍정적인 성품</strong>을 가지고 있는 사람입니다.</li>
    <li> 전 운동을 좋아하며 <strong>스트레스 관리</strong>를 잘하는 사람입니다.</li>
    <li> 전 <strong>몰입</strong>을 좋아하며, 관심 분야의 지식이 쉽게 얻어지지 않을때 <strong>파고들어 쟁취하는</strong> 사람입니다.</li>
    </ul>
  </div>
</div>

<div id="skill">
<h1 class="skillSetTitle">Skillset</h1>
<div class="skillSetContainer">
  <div class="skillSetBorder">
    <img src="/assets/js.png" alt="js"/>
  </div>
 <div class="skillSetBorder">
    <img src="/assets/ts.png" alt="ts"/>
  </div>
 <div class="skillSetBorder">
    <img src="/assets/git.png" alt="git"/>
  </div>
   <div class="skillSetBorder">
    <img src="/assets/html.png" alt="html"/>
  </div>
   <div class="skillSetBorder">
    <img src="/assets/react.png" alt="react"/>
    </div>
    <div class="skillSetBorder">
    <img src="/assets/learning.png" alt="learning"/>
    </div>
    <div class="skillSetBorder">
      <img src="/assets/learning.png" alt="learning"/>
    </div>
    <div class="skillSetBorder">
      <img src="/assets/learning.png" alt="learning"/>
    </div>
</div>
</div>

<style>
  body {
    min-height: 825px;
  }

#introContainer{
  display:flex;
  gap: 30px;
}

.introduction {
  flex: 1 1;

  }
#skill {
  padding: 1.5em;
}

.skillSetTitle{
  text-align: center;
}
.skillSetContainer {
  display:flex;
  flex-wrap: wrap;
  gap:30px;
  margin-top: 30px;
}


.skillSetBorder{
  flex: 1 1 auto;
  width:18%;
  border: 1.7px solid rgba(200,137,230,.637);
  border-radius: 5px;
  padding: 10px;
}

.skillSetBorder:hover{
  -webkit-transform: scale(1.05) !important;
	transform: scale(1.05) !important;
}

</style>
