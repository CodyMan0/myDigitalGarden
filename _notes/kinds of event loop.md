---
---

-   **window event loop**  
    - 같은 origin인 모든 윈도우는 윈도우 이벤트 루프를 공유한다.  
    - 모든 윈도우들은 동기적으로 소통할 수 있게 된다.
-   **worker event loop**  
    - window event loop와는 독립적으로 실행된다.
-   **worklet event loop**