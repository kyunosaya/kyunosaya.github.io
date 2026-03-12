---
layout: single
title:  "무선 디버깅 셋팅하기"
categories: 
  - development
---

# 안드로이드 무선 디버깅하기 전 셋팅 과정

항상 유선으로 디버깅을 해왔는데, 어느 날부터인가 Offline으로 나오고 디바이스와 연결이 도통 되지를 않았다.  
유선으로 하면 복잡하게 뭔가 설정을 만지고 뭘 더 할 건 없으니 빠르지만...  
이런 경우가 생길 수 있으니 알아둬야겠다 싶었다.  
+ 2026-031-12 추가 : USB 디버깅이 안 됐던 이유는, <b>디바이스의 절전모드</b>때문이었다.   
  무선 디버깅은 잘 되길래 그러려니 했는데, 어느 날부터 무선 디버깅도 잘 안되기 시작했다.  
  QR로 연결하는 방법도 써보고, 핸드폰을 바꾸게 되면서 핸드폰 문제가 아니란 것도 알게 되었다.  
  QR로 연결할 때, vsc의 ADB QR 확장자를 사용하는데, 이 때 안내 문구에 디바이스가 오프라인이라고 나오면서 연결이 안되는 것이었다.  
  그럼 디바이스 문제구나, 라는걸 알았고 챗지피티한테 물어봤다.  
  챗지피티는 원인이 여러 가지라며 설명을 해줬고, 원인 중 하나인 <b>폰이 네트워크 바뀌거나 절전으로 연결이 죽음</b>이라는 내용을 보고 '절전모드 때문일 수도 있겠다..!' 라는 생각이 번뜩 들었다.  
  그래서 핸드폰의 절전모드를 꺼주니 웬걸... 두 핸드폰 모두 바로 USB디버깅도 되고 무선디버깅도 됐다.  
  결과는 허무하지만 그 과정에서 여러 가지 해본 것이 좋은 경험으로 잡힌 것 같다.  
  디버깅 전엔 꼭... 절전모드를 끄도록 해야겠다.  
  답답했던 부분이 뻥 뚫린 것 같다서 기쁘다.  
<br>
<br>
<a href="https://developer.android.com/tools/releases/platform-tools?hl=ko" target="_blank" rel="noopener noreferrer">
  <strong>ADB (Android Debug Bridge) 다운로드 사이트</strong>
</a>  
위 사이트에서 adb 최신버전을 다운받는다. (나는 Window용을 다운받았다.)  
<br>
<img width="700" height="520" alt="image" src="https://github.com/user-attachments/assets/1b0aa004-c1c6-4f06-b0de-bd994baa6cdc" />  
<br>
<img width="526" height="146" alt="image" src="https://github.com/user-attachments/assets/680e01a1-8911-4396-a87b-e20f160cfbe7" />  
<br>
<img width="606" height="599" alt="image" src="https://github.com/user-attachments/assets/82a7047b-7356-4432-bcca-993271776d74" />  
<br>
<img width="1088" height="760" alt="image" src="https://github.com/user-attachments/assets/090b9465-8510-4270-b2cd-005db37e63b6" />  
<br>
파일 압축 해제하면 준비는 끝 !  
<br>
<br>
<img width="566" height="525" alt="image" src="https://github.com/user-attachments/assets/54a13a3c-55f4-4913-af96-40b78310b7a4" />  
<br>
<img width="583" height="187" alt="image" src="https://github.com/user-attachments/assets/7c17340d-8a43-49a4-9618-f0e8a0931af2" />  
<br>
<img width="614" height="705" alt="image" src="https://github.com/user-attachments/assets/20f8ebef-1e96-4d4f-8097-9d6490a3e7ec" />  
<br>
<img width="595" height="703" alt="image" src="https://github.com/user-attachments/assets/620b803c-fab3-41d3-8131-89256cf14b52" />  
<br>
**내 PC 마우스 우측 클릭 > 속성 > 고급 시스템 설정 보기 > 환경 변수(N) > 시스템 변수(S)**  
<br>
<br>
<img width="550" height="336" alt="image" src="https://github.com/user-attachments/assets/b66be356-4193-48d9-bab9-88228ee9ecb8" />  
<br>
<img width="842" height="219" alt="image" src="https://github.com/user-attachments/assets/ae8046bc-9b18-4610-8a4c-b385b9f6168f" />  
<br>
<img width="552" height="258" alt="image" src="https://github.com/user-attachments/assets/2f093cbd-f13a-45c4-b608-be8aad259d89" />  
<br>
**새로 만들기(W) > 변수 이름 : adb / 변수 값 : 아까 다운로드 받은 파일 경로 > 확인**  
<br>
<br>
<img width="549" height="264" alt="image" src="https://github.com/user-attachments/assets/78b100dd-8465-430e-a726-d8737b1b8dcf" />  
<br>
<img width="665" height="228" alt="image" src="https://github.com/user-attachments/assets/db790328-ff25-4622-8a68-015c5776b5ae" />  
<br>
<img width="666" height="654" alt="image" src="https://github.com/user-attachments/assets/b741b6ba-fdcf-4aa3-a99f-e933a4218fdb" />  
<br>
**변수 Path 선택 > 편집(I) > 새로 만들기(N) > %adb%\ 입력 > 확인**  
<br>
<br>
<img width="583" height="653" alt="image" src="https://github.com/user-attachments/assets/1fdc9f43-efee-47da-897b-60d8ca9ce60a" />  
<br>
<img width="614" height="697" alt="image" src="https://github.com/user-attachments/assets/c5a34750-4833-4386-969b-e72a1ce6eb78" />  
<br>
그리고 최종적으로 확인버튼 누르고 저장 !  
<br>
<br>
<img width="573" height="139" alt="image" src="https://github.com/user-attachments/assets/84167eb0-61ef-4f83-92ac-0b34a5d928ad" />  
<br>
그러면 cmd에서 adb pair, adb connect... 이런 식으로 사용 가능하다 !  
무선 디버깅 시 작성 커멘드는 [요기 클릭해서 이동!](https://kyunosaya.github.io/development/01-wireless-debugging-try/)  
<br>
<br>
<br>
참고 사이트 :
<a href="https://taeheum.tistory.com/191" target="_blank" rel="noopener noreferrer">
  https://taeheum.tistory.com/191
</a>  
