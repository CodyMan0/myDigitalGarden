---
aliases: []
tags : 
---
Up : [[HOME π]]

μΆμ² : λͺ¨λ μλ°μ€ν¬λ¦½νΈ 
μ μ :
URL : 
1. https://ko.javascript.info/event-loop
2. https://chanmi-lee.github.io/articles/2020-06/JavaScript-Visualized-Event-Loop
3. [Velog λΈλ‘κ·Έ](https://velog.io/@yejineee/%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A3%A8%ED%94%84%EC%99%80-%ED%83%9C%EC%8A%A4%ED%81%AC-%ED%81%90-%EB%A7%88%EC%9D%B4%ED%81%AC%EB%A1%9C-%ED%83%9C%EC%8A%A4%ED%81%AC-%EB%A7%A4%ED%81%AC%EB%A1%9C-%ED%83%9C%EC%8A%A4%ED%81%AC-g6f0joxx)
μΈμ© : 

νλ§λ μ λ¦¬ 
0. μ΄λ²€νΈ λ£¨νλ μ½ μ€νμ λͺ¨λν°νκ³  νμ€ν¬ νμμ μνν  μμμ΄ μλμ§ νμΈνλ λ¨μΌ μ€λ λ λ£¨νμλλ€. μ½ μ€νμ΄ λΉμ΄ μκ³  νμ€ν¬ νμ μ½λ°± ν¨μκ° μλ κ²½μ°, ν¨μλ νμμ μ κ±°λκ³  μ€νλ  μ½ μ€νμΌλ‘ νΈμλ©λλ€.

1. μ νμ?  μλ°μ€ν¬λ¦½νΈλ μ±κΈ μ€λ λ κΈ°λ°μ μΈμ΄μ§λ§,Β **μλ°μ€ν¬λ¦½νΈκ° κ΅¬λλλ νκ²½(Node.js, λΈλΌμ°μ )μ μ¬λ¬ μ€λ λκ° μ¬μ©**λλ€.Β **μ¬λ¬ μ€λ λκ°μ¬μ©λλ κ΅¬λ νκ²½μ΄ μλ°μ€ν¬λ¦½νΈ μμ§κ³Ό μ°λνκΈ° μν΄ μ¬μ©λλ μ₯μΉκ° 'μ΄λ²€νΈ λ£¨ν'**Β μ΄λ€. [[λ©μΈ μ€λ λ μ­ν ]]
3. μ μ?  μ΄λ²€νΈ λ£¨νλ νμ€ν¬ νμ μλ μ½λ°±ν¨μλ₯Ό μ½ μ€νμ μ°λμν€λ κ²μ λ§νλ€. 

-> my language : μ±κΈμ€λ λ μΈμ΄μΈ μλ°μ€ν¬λ¦½νΈμ λμμ±μ λΆμ¬νκΈ° μν΄μ μ¬μ©λλκ²μ΄ μ΄λ²€νΈ λ£¨ν!! 

[[OS Moc]]μ λΉμ·νλ€κ³  λκ»΄μ§λ€.
# λͺ¨λ μλ°μ€ν¬λ¦½νΈ


μ΅μ νλ μ¬λ°λ₯Έ μν€νμ² μ€κ³λ₯Ό νκΈ° μν΄μ μμμΌνλ κ². 

μλ°μ€ν¬λ¦½νΈ μμ§μ΄ λμκ°λ μκ³ λ¦¬μ¦μ μΌλ°ν

1.  μ²λ¦¬ν΄μΌ ν  νμ€ν¬κ° μλ κ²½μ°:
    -   λ¨Όμ  λ€μ΄μ¨ νμ€ν¬λΆν° μμ°¨μ μΌλ‘ μ²λ¦¬ν¨
2.  μ²λ¦¬ν΄μΌ ν  νμ€ν¬κ° μλ κ²½μ°:
    -   μ λ€μ΄ μλ€κ° μλ‘μ΄ νμ€ν¬κ° μΆκ°λλ©΄ λ€μ 1λ‘ λμκ°

λνμ μΈ νμ€ν¬ 
-   μΈλΆ μ€ν¬λ¦½νΈμΈ script μ½λκ° μ΄ μ€ν¬λ¦½νΈλ₯Ό μ€ννλ κ²
-   μ¬μ©μκ° λ§μ°μ€λ₯Ό μμ§μΌ λΒ `mousemove`Β μ΄λ²€νΈμ μ΄λ²€νΈ νΈλ€λ¬λ₯Ό μ€ννλ κ²
-   `setTimeout`μμ μ€μ ν μκ°μ΄ λ€ λ κ²½μ°, μ½λ°± ν¨μλ₯Ό μ€ννλ κ²

[[λ§μ΄ν¬λ‘ νμ€ν¬ vs λ©ν¬λ‘ νμ€ν¬]]
νμ€νΈ νλ λκ°λ‘ λλλ€.
1. [[micro_task_queue]]μλ λΉλκΈ° μ λ€μ΄ λ€μ΄κ°λκ±΄κ°? 
2. [[λ§μ΄ν¬λ‘νμ€ν¬ ν]]

μ λ¦¬ -> μ½μ€ν -> λ§μ΄ν¬λ‘ ν -> λ§€ν¬λ‘ ν μμΌλ‘ μ€ν!! 

### μ€λ¬΄ μ¬λ‘ 
1. CPU μλͺ¨κ° λ§μ νμ€ν¬ μͺΌκ°κΈ° 


# Dev μλ£
μλ°μ€ν¬λ¦½νΈλ μ±κΈ μ€λ λ -> λ¬΄κ±°μ΄ νλμ λμμ΄ λμν λ μλ¬΄κ²λ λΌμ΄λ€μ§ λͺ»ν΄ -> avaScript μμ§ μμ²΄μμ μ κ³΅νμ§ μλ μΌλΆ κΈ°λ₯μΈΒ `Web API`λ₯Ό μ κ³΅νλ―λ‘μ¨ λΉλκΈ° μ κ³΅ -> 



# λ²¨λ‘κ·Έ
-   **μλ°μ€ν¬λ¦½νΈ μμ§**  
    -Β [[Heap]]Β : κ°μ²΄λ€μ ν λ©λͺ¨λ¦¬μ ν λΉλλ€. ν¬κΈ°κ° λμ μΌλ‘ λ³νλ κ°λ€μ μ°Έμ‘° κ°μ κ°κ³  μλ€.
    -Β [[call stack]]Β : ν¨μ νΈμΆ μ, μ€ν μ»¨νμ€νΈκ° μμ±λλ©°, μ΄λ¬ν [[Execution Context]]λ€μ΄ μ½ μ€νμ κ΅¬μ±νλ€.
-   **Web API or Browser API**  
    - μΉ λΈλΌμ°μ μ κ΅¬νλ APIμ΄λ€.  
    - DOM event, [[AJAX]], Timer λ±μ΄ μλ€.
-   **μ΄λ²€νΈ λ£¨ν**  
    - μ½ μ€νμ΄ λΉμλ€λ©΄, νμ€ν¬ νμ μλ μ½λ°± ν¨μλ₯Ό μ²λ¦¬νλ€.
-   **νμ€ν¬ ν**  
    - μ΄λ²€νΈ λ£¨νλ νλ μ΄μμ νμ€ν¬ νλ₯Ό κ°λλ€.  
    - νμ€ν¬ νλΒ **νμ€ν¬μ Set**μ΄λ€.  
    - μ΄λ²€νΈ λ£¨νκ° νμ μ²« λ²μ§Έ νμ€ν¬λ₯Ό κ°μ Έμ€λ κ²μ΄ μλλΌ, νμ€ν¬ νμμ μ€ν κ°λ₯ν(runnable) μ²« λ²μ§Έ νμ€ν¬λ₯Ό κ°μ Έμ€λ κ²μ΄λ€. νμ€ν¬ μ€μμ κ°μ₯ μ€λλ νμ€ν¬λ₯Ό κ°μ Έμ¨λ€. [[FIFO(μ μμ μΆ)]]

λΈλΌμ°μ μ Node.jsμμ κ³΅ν΅μΌλ‘ μ κ³΅νλ κ²μ΄Β **μ΄λ²€νΈ λ£¨ν**  [[μΉ λΈλΌμ°μ μ λΈλμ μ°¨μ΄]]λ μ κ³΅ν΄μ£Όλ 


### μκ°μ μ°κ²°κ³ λ¦¬
λΆμΌ :

ν€μλ :

κ΄λ ¨μλ λ©λͺ¨ :
