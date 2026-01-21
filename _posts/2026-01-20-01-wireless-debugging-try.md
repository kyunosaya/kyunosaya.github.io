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
![image.png](attachment:489107d4-3ecc-4ac9-823e-5302f854eec7:image.png)  
<br>
![image.png](attachment:523ee1de-5efb-4e56-8d9f-cb56a9cb163b:image.png)  
<br>
![image.png](attachment:fc462aaa-dec2-4a49-a066-81e9d6a8ed16:image.png)  
<br>
이런 식으로 해당 폴더에 들어가서 cmd를 키면 바로 해당 디렉토리로 접속이 된다.  
이런 방식이 아닌 그냥 cmd를 실행시키려고 한다면,  
<br>
![image.png](attachment:86e30939-57b7-4490-831b-1f7134c5e34a:image.png)  
<br>
![image.png](attachment:7487515c-6306-4e2c-b652-3349a5b207ad:image.png)  
<br>
![image.png](attachment:ec38afb4-cb72-47ef-b23c-1f6fc532ae84:image.png)  
<br>
![image.png](attachment:37e8fee5-032b-4fee-ac11-872469d57aa1:image.png)  
<br>
![image.png](attachment:93b6a1ff-1f70-4067-8c32-429cd03e7936:image.png)  
<br>
![image.png](attachment:60265b94-6192-4f01-b5ff-8eec0ceeda8a:image.png)  
<br>
dir 명령어를 사용해서 디렉토리 목록을 보면서,  
cd 명령어로 디렉토리 이동을 해주면 된다.  
<br>
<br>
![image.png](attachment:21c36e4b-59df-489d-83ba-6033f762a12f:image.png)  
<br>
해당 디렉토리로 이동하고 dir 명령어로 디렉토리 목록을 조회해서 **'adv.exe'**가 있는지 확인해주면 된다 !  
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
![Screenshot_20260121_101901_Settings.jpg](attachment:1c558db0-3726-4bc0-89cb-21165aa253cb:Screenshot_20260121_101901_Settings.jpg)  
무선 디버깅을 누르면 아래 이미지와 같이 화면 이동 된다.  
거기서 '페어링 코드로 기기 페어링'을 눌러주면 페어링에 필요한 IP주소 및 포트와 인증번호가 나온다.  
<br>
![Screenshot_20260121_101938_Settings.jpg](attachment:4a4fe156-d5ff-4030-aba5-27f06f210d3c:Screenshot_20260121_101938_Settings.jpg)  
<br>
![Screenshot_20260121_102230_Settings.jpg](attachment:d93280e8-5724-4e0d-ae5e-e5d8f1212562:Screenshot_20260121_102230_Settings.jpg)  
<br>
위 정보를 가지고 페어링해줄거니까 cmd를 다시 실행시키자.  
<br>
<br>
![image.png](attachment:0f147cc1-800c-4b15-9bbc-75a502c94ed9:image.png)  
**adb pair IP주소 및 포트번호** 입력 후 엔터,    
**그리고 code 입력 칸에는 모바일에 나왔던 암호코드를 입력해준다.**  
성공하면 Successfully paired... 하면서 안내 문구가 출력된다.  
<br>
<br>

## 디바이스 커넥트
이제 커넥트(연결)을 해줘야한다.  

