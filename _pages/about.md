---
layout: page
title: About
permalink: /about
---

<div id="introContainer">
  <div class='introduction'>
    <h1 class="skillSetTitle">BACKGROUND π</h1>
    <p>μλνμΈμ. μμΈ κ΄μ§κ΅¬μ κ±°μ£Όνκ³  μλ νλ‘ νΈμλ κ°λ°μ μ΄μ£Όμμλλ€.<br>μ λ μλ¬Ένμ μ κ³΅μΌλ‘ νμμ΅λλ€.νμ§λ§ μ°μ°μΉμκ² νλ‘κ·Έλλ° μλ¬Έμ΄λΌλ κ΅μ μμμ λ£κ³  νλ‘κ·Έλλ°μ λν΄ κ΄μ¬μ κ°μ§κ² λμμ΅λλ€.
    <br>
    theOdinProjectμ΄λΌλ μ€νμμ€λ₯Ό νμ©νμ¬ 3κ°μκ° <strong>λν</strong>μ νμκ³  μ΄ν ννλ‘μ νΈ κ²½νμ μν΄ <strong>λΆνΈμΊ ν</strong>λ₯Ό μ§ννλ©΄μ κ°λ°μμ μ­λμ ν€μ°λλ° λΈλ ₯νμ΅λλ€. κ·Έ ν νλ¬κ° μν°λ νλ¦¬μ¨λ³΄λ© μ½μ€λ₯Ό ν΅ν΄ μλ‘μ΄ κΈ°μ μ μ¬μ©ν΄λ³΄λ©° λ€μνκ² νμ΅νμμ΅λλ€. κ·Έ λμ λ°°μ λ κ²λ€μ μ λ¦¬νλ©° μ±λ¦°μ§ν μν©μ λ§μ΄ν  μ€λΉλ₯Ό νκ³  μμ΅λλ€.
    </p>
  </div>
  <div class='introduction'>
    <h1 class="skillSetTitle">KNOW WHO I'M  π±</h1>
    <ul>
    <li> μ  μ£Όλ³ μ¬λλ€μκ² <strong>μλμ§</strong>λ₯Ό μ£Όλ μ¬λμλλ€. </li>
    <li> μ  <strong>κ³΅κ°λ ₯μ΄</strong> λ°μ΄λ <strong>νμ λ₯λ ₯</strong>μ΄ λ°μ΄λ μ¬λμλλ€. </li>
    <li> μ  <strong>λ°κ³  κΈμ μ μΈ μ±ν</strong>μ κ°μ§κ³  μλ μ¬λμλλ€.</li>
    <li> μ  μ΄λμ μ’μνλ©° <strong>μ€νΈλ μ€ κ΄λ¦¬</strong>λ₯Ό μνλ μ¬λμλλ€.</li>
    <li> μ  <strong>λͺ°μ</strong>μ μ’μνλ©°, κ΄μ¬ λΆμΌμ μ§μμ΄ μ½κ² μ»μ΄μ§μ§ μμλ <strong>νκ³ λ€μ΄ μμ·¨νλ</strong> μ¬λμλλ€.</li>
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
    <img src="/assets/node.png" alt="node"/>
    </div>
    <div class="skillSetBorder">
      <img src="/assets/recoil.png" alt="recoil"/>
    </div>
    <div class="skillSetBorder">
      <img src="/assets/aws.png" alt="aws"/>
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


  @media (max-width: 450px) {
    #introContainer{
      display:flex;
      flex-direction: column;
      gap: 30px;
    }
    .introduction {
  }
  
  }

</style>
