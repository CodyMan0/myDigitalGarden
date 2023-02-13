---
layout: page
title: Home
id: home
permalink: /
---

# 안녕하세요~ 👋

## 전 프론트엔드 개발자 이주영(Brian)입니다.

<div id="indexContainer">
<div class="introContainer" >
<li style="padding: 1.5em 1em;">
  저의 PDF 이력서는 👉 <a href="/assets/주도적인 프론트엔드 개발자 이주영" style="font-weight: bold" download>Download RESUME</a>
</li>
<li style="padding: 1.5em 1em;"> 
  전 이런 사람이에요 👉 <a class="internal-link" href="/about"><b>About me</b></a>
</li>
<li style="padding: 1.5em 1em;">
  저의 포트폴리오는 👉 :  <a class="internal-link" href="/portfolio"><b>Portfolio</b></a>
</li>
<li style="padding: 1.5em 1em;">
  개발 지식 저장소는  👉 :  <a class="internal-link" href="/knowledge-mocs"><b>myDigitalGarden</b></a>
</li>
</div>
<div class="imgContainer">
<img class="image-container" src="/assets/presentation.png"/>
</div>
</div>

<style>
  body {
    min-height: 710px;
  }

  #indexContainer {
    display:flex;
    flex-direction: row;
    margin-top: 1.5em;
  }

  .introContainer {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  .imgContainer {
    flex: 1;
  }

  .image-container {
    max-height: 50vh;
  }

  @media (max-width: 450px) {
    .imgContainer {
      display:none;
    }
  }
</style>
