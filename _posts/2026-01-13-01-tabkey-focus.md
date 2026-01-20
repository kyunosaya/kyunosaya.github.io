---
layout: single
title:  "Tab키 포커스 제어 방법"
categories: 
  - development
---

# tabindex 속성 이용해서 Tab키 포커스 제어하기


화면 테스트를 하다가 Tab키를 누른 후 Enter키를 누르면 버튼이 선택이 된다.  
여러 문제가 있지만 가장 큰 건 비활성화된 상태의 버튼도 클릭이 된다는 것. (spiderGen 기준)  
굳이 Tab키를 살려둘 이유도 없기에 막기로 했다.  

간단하게도 버튼 컴포넌트에 tabindex속성을 넣어주기만 하면 된다!  

```html
<button style="..." tabindex="-1"></button>
```
