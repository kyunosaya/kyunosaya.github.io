---
layout: single
title:  "무선 디버깅 디바이스 연결하기"
categories: 
  - development
---

# 안드로이드 무선 디버기하기 위해 디바이스 연결 과정  
<br>

## cmd 준비  
앞에서 셋팅을 했다면, 이제 cmd에서 커넥트를 해줘야한다.  
cmd를 실행시켜줄건데,  
<br>
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/01.png" width="700">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/02.png" width="700">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/03.png" width="600">  
<br>
이런 식으로 해당 폴더에 들어가서 cmd를 키면 바로 해당 디렉토리로 접속이 된다.  
이런 방식이 아닌 그냥 cmd를 실행시키려고 한다면,  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/04.png" width="600">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/05.png" width="600">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/06.png" width="600">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/07.png" width="250">  
나의 경우는 현재 디렉토리를 빠져나와야지 adb.exe 파일이 있는 디렉토리로 이동할 수 있기 때문에  
cd ..로 빠져나왔다.  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/08.png" width="600">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/09.png" width="600">  
<br>
dir 명령어를 사용해서 디렉토리 목록을 보면서,  
cd 명령어로 디렉토리 이동을 해주면 된다.  
<br>
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/10.png" width="600">  
<br>
해당 디렉토리로 이동하고 dir 명령어로 디렉토리 목록을 조회해서 **adv.exe**가 있는지 확인해주면 된다 !  
자, 이제부터 페어링 및 커넥트를 해줄 차례다.  
<br>
<br>

## 디바이스 페어링  
페어링이란, 한 마디로 **인증 단계**라고 보면 된다.  
기기끼리 인식하고 안전하게 연결되도록 정보를 교환, 등록하는 (초기)설정 과정이다.  
<br>
먼저, 모바일에서 무선 디버깅 모드를 활성화시켜놔야한다.  
개발자 옵션 활성화시키는 방법은 기기마다 다르기 때문에, 서치해서 찾아보면 정보가 많이 나오니 참고하면 될 것 같다 !  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/11.jpg" width="400">  
무선 디버깅을 누르면 아래 이미지와 같이 화면 이동 된다.  
거기서 '페어링 코드로 기기 페어링'을 눌러주면 페어링에 필요한 IP주소 및 포트와 인증번호가 나온다.  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/12.jpg" width="400">  
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/13.jpg" width="400">  
<br>
위 정보를 가지고 페어링해줄거니까 cmd를 다시 실행시키자.  
<br>
<br>
<img src="/assets/images/posts/2026-01-20-01-wireless-debugging-try/14.png" width="600">  
**adb pair IP주소 및 포트번호** 입력 후 엔터,    
**그리고 code 입력 칸에는 모바일에 나왔던 암호코드를 입력해준다.**  
성공하면 Successfully paired... 하면서 안내 문구가 출력된다.  
<br>
<br>

## 디바이스 커넥트
이제 커넥트(연결)을 해줘야한다.  

