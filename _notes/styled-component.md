---
---


---
aliases: []
tags : 
---
Up : [[HOME π]]

μΆμ² :
μ μ :
URL : 
μΈμ© : 


### λ΄λΆ μλ¦¬

```jsx
const red = 'λΉ¨κ°μ';
const blue = 'νλμ';

function favoriteColors(texts, ...values) {
   return texts.reduce((result, text, i) => 
   `${result}${text}${values[i] ? `<b>${values[i]}</b>` : ''}`, '');
}

favoriteColors`μ κ° μ’μνλ μμ ${red}κ³Ό ${blue}μλλ€.`

// μ κ° μ’μνλ μμ <b>λΉ¨κ°μ</b>κ³Ό <b>νλμ</b>μλλ€.
```

styled-componenetλ λ°νμμ μ€νμΌμ΄ μμ΄μ§λ€



### μκ°μ μ°κ²°κ³ λ¦¬
λΆμΌ : [[runtime]]

ν€μλ :

κ΄λ ¨μλ λ©λͺ¨ :


