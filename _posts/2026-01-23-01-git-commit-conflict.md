---
layout: single
title:  "git pull받을 때 나오는 에러"
categories: 
  - development
---

# git 충돌 시 대처하는 방법  
사실 협업을 하다보면 git 충돌은 정말 흔한 일이다.  
내가 작성하는 충돌의 경로는, **같은 줄 또는 같은 블록**을 수정했을 경우다.  
<br>
화면을 수정하다 보면 남의 화면을 나도 모르게 건들고 모르고 commit을 하는 경우들이 있을 수도 있다.  
혹은 pull받는 걸 깜빡하고 개발을 한다거나, 아니면 내가 수정 중인 경우에 다른 누군가가 내가 수정 중인 파일을 수정하거나...  
아무튼 그런 경우, 충돌이 났을 때 어떻게 하는지 알아야할 것 같았다.  
나같은 경우에는 그냥 내가 수정한 파일을 로컬에 따로 빼놓고 pull받고 다시 넣고... 단순하게 그렇게 해왔다.  
그게 틀린 것은 아니겠지만, 그런 방법이 아닌 다른 방법 또한 알아놔야 추후에 대처가 가능할 것 같았다.  
<br>
<br>

#### 에러 구현하기
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/01.png" width="400">  
이런 에러, 정말 수도 없이 봐왔다.....  
협업하면 무조건 보는 에러가 아닐까 싶다.  
<br>
해당 에러를 구현하기 위해서 나는  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/07.png" width="500">  
github 에서 해당 줄을 수정하고 커밋했고,  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/06.png" width="500">  
vsc에서 이런 식으로 수정을 해놓고 pull을 받으려고 했다.  
<br>
그 상태에서 pull을 받으니 해당 에러가 떴다.  
<br>
<br>

#### 에러 대응하기  
일단 나는 TortoiseGit를 사용하고 있다.  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/02.png" width="500">  
Stash Change를 눌러주면,  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/10.png" width="500">  
요런 창이 뜨는데, 알맞는 메세지를 입력하고 ok를 눌러준다.  
<br>
**Stash Change란 ?**  
**지금 작업 중인 변경사항을 "임시 서랍"에 넣어두는 기능**이다.  
<br>
<img width="274" height="343" alt="image" src="https://github.com/user-attachments/assets/65498a19-fe9f-4355-9027-2542f5360428" />  
터미널에서 열어준다.  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/11.png" width="500">  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/12.png" width="500">  
**git stash list**를 치면, stash했던 파일 리스트가 나온다.  
참고로 git status는 지금 Git이 뭘 보고 있고, 뭘 기다리고 있는지 알려주는 명령어다.  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/13.png" width="500">  
**git stash apply**입력 후 엔터치면 해당 파일이 다시 로컬에서 보여질 것이다.  
git stash apply는 가장 최근 것을 가지고 온다.  
다른 stash를 가지고 오고 싶다면, **git stash apply stash@{0}** 이런식으로 써주면 된다.  
다만, power shell은 "stash@{0}" , 따옴표(")를 붙여줘야 인식되는 것 같다.  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/15.png" width="500">  
그럼 요로케~ 수정된 내용을 가지고 오고 충돌이 나게 되어있다.  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/16.png" width="500">  
vsc에서 열어보면 이런 식으로 되어있다!  
여기서 어떤 소스로 덮어쓸 것인지 골라주면 된다.  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/17-1.png" width="500">  
Accept Current Change :   
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/17-2.png" width="500">  
Accept Incoming Change :  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/17-3.png" width="500">  
Accept Both Chagnes :  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/17-4.png" width="500">  
Compate Changes :  
<br>
난 Accept Incoming Change를 해줬다.  
<br>
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/18.png" width="500">  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/19.png" width="500">  
이 상태로 커밋누르고 뜨는 창에서 Ignore를 클릭하면 끝 !  
<br>
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/20.png" width="500">  
<img src="/assets/images/posts/2026-01-23-01-git-commit-conflict/21.png" width="500">  
github에서 보면, 이런 식으로 commit한 내용이 나온다.  
<br>
<br>
git이 충돌나는 경우는 흔하니까 이런 지식을 알아두면 유용하게 적용되지 않을까 싶어서 찾아봤다.  
포스팅 끝 ! 
