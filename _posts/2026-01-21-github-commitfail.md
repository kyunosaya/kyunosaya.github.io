---
layout: single
title:  "깃허브 블로그 스타일 지정 시 한 실수"
categories: 
  - notes
---

스타일을 요리조리 바꿔봐도 이상하게 적용이 되질 않았다.  
캐시 삭제를 하고 다시 커밋을 해도 죽어도 안됐었다.  
대체 원인이 뭔가... 하고 보다가 github에서 x표시가 있는 것을 봤다.  
<img width="288" height="70" alt="image" src="https://github.com/user-attachments/assets/8e77167b-6ec6-4374-9811-350696181e57" />  
(아니 이게 뭐시여)  
<br>
<img width="579" height="173" alt="image" src="https://github.com/user-attachments/assets/21b1d45d-b373-4aa1-a950-4aaaae6ddc2e" />  
<br>
<img width="751" height="40" alt="image" src="https://github.com/user-attachments/assets/cbdd5727-c778-47b7-984e-4542fa93eb85" />  
내가 뭔가 잘 못 작성했구나, 하고 내가 만든 스킨용 scss파일을 봤는데,  
<br>
<img width="417" height="678" alt="image" src="https://github.com/user-attachments/assets/24d03c21-0874-4550-8f5c-296bef601402" />  
변수 선언할 때만 쓰는 **!default**를 속성에 쓰고 있었다고 한다.  
속성에는 **!important**를 써야하는데(혹은 생략하거나) 변수 끌어쓰면서 저렇게 작성한 것 같다.  
<br>
근데 나는 scss를 처음 써봤기에 **!default**를 속성에 쓰면 안되는지 몰랐다.  
css에서는 없는 키워드니까...  
그도 그럴게 css에는 없으니까...ㅎ  
<br>
이번 기회에 정확하게 배웠다.  
**!default는 sacc전용 키워드이고, 변수 선언 전용 키워드이다.**  
