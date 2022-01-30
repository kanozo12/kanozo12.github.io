---
title: "원숭이도 따라하는 Git & GitHub (1)"
excerpt: "원숭이도 따라하는 시리즈 깃허브 첫 번째 포스트"
toc: true
toc_sticky: true

categories:
  - Git
tags:
  - Git
  - Github
last_modified_at: 2022-01-27T12:06:00
---

이 포스트는 원숭이도 따라하는 Git & GitHub 시리즈의 첫 번째 포스트이다.
Git 과 GitHub가 무엇인지 알아 보기 앞서 버전관리가 무엇인지 부터 알아볼 것이다.

### **버전관리**

팀 프로젝트에서 사용할 공용폴더를 만들고 그곳에 소스코드를 올린다고 가정했을 때,
이곳에 올려진 소스코드를 "Test 버전 00"이라고 정하겠다.
팀원 Jack이 "Test 버전"의 소스코드를 수정해 "수정 버전 01"으로 저장하고 팀원 Beer가 "수정 버전 01"을 수정하여 "최종 버전 02"으로 저장 할 수 있을 것이다. <br><br>
이와 같이 최종 버전을 기준으로 수정하고 순차적으로 번호를 붙여 저장하면 버전관리가 될 것이다. 그런데 팀원 Jack과 Beer가 동시에 "수정 버전 01"을 수정해서 "수정 버전 02"로 저장 한다면 어떻게 될까, 이처럼 협업이 필요한 개발작업에선 버전관리가 필수이다. 

### **로컬저장소 만들기**
버전관리 할 프로젝트 폴더에 아래와 같은 명령어를 입력한다.
```
  git init
```

![git](/assets/images/monkey_1_gitinit.png)

위와 같이 "Initialized empty Git repository" 라는 문구가 나오면 깃을 사용할 준비가 끝난다. git init 명령어를 입력하면 해당 폴더에 [.git]라는 폴더가 생성되는데 이곳에는 원격저장소 정보 및 버전 정보들이 기록된다. 이를 로컬저장소라 한다.

### **원격저장소 업로드**
원격저장소에 업로드 하기 위해 먼저 로컬 저장소에 내 깃허브 계정 정보를 등록해야 한다. 이 정보를 통해 원격저장소에선 누가 어떤 버전을 만들었는지 알 수 있다. 계정 정보 등록을 위해 다음 명령어를 입력한다.
```
  git config --global user.email "Github Email"
  git config --global user.name "UserName"
```

![git](/assets/images/monkey_1_gitinit_2.png)
<br>
원격저장소에 업로드 할 README.txt 파일을 만들어준다.

```
  git add README.txt
  
  git commit -m "설명 추가"
```
위와 같이 add로 업로드할 파일을 추가해주고 commit으로 저장한 파일을 원격저장소에 올리기 위해 반영해준다.

아래와 같은 메시지가 보이게 된다면 원격저장소에 올릴 준비가 모두 끝났다.
![git](/assets/images/monkey_1_gitinit_3.png)

```
  git push origin master
```
위의 명령어는 push 명령어를 실행하여 origin이라는 원격 저장소의 master 브랜치에 저장한 commit을 업로드 하겠다는 의미이다.

다음과 같은 결과가 나오면 원격저장소에 업로드를 성공한 것이다. 
![git](/assets/images/monkey_1_gitinit_4.png)

원격저장소로 접속하여 결과를 확인해보자.
![git](/assets/images/monkey_1_gitinit_5.png)
앞서 작성한 README.txt 파일의 내용이 정상적으로 원격저장소에 업로드 된 것을 확인할 수 있다.
<br><br>
추가로 README.txt라는 이름의 파일을 업로드 하면 깃허브에서 자동으로 파일 안의 내용이 리포지터리 설명글로 바뀐다. 

### **Commit간의 이동**
우리는 미리 저장해둔 Commit으로 이동할 수 있다. 개발을 하다 작업 중인 소스코드에 버그나 이슈가 생겨 이전 Commit부터 다시 작업 하고 싶다면
Git을 이용해 언제든 해당 Commit으로 이동 할 수 있다.


Commit간의 이동을 살펴보기 위해 위에서 작성한 "설명 추가" Commit에 다른 Commit을 추가해 보겠다.
![git](/assets/images/monkey_1_gitinit_6.png)

위와 같이 README.txt 파일을 수정하고
```
  git add *
  
  git commit -m "설명글 수정"
```
add과 Commit 명령어를 실행한다. (* 는 해당 디렉토리의 모든 파일을 저장한다는 의미이다.)

이제 로컬 저장소에는 최초에 저장했던 "설명 추가" 라는 이름의 커밋과 "설명글 수정" 이라는 두개의 커밋이 존재 하게 된다.
로컬 저장소에 있는 커밋을 확인하고 싶다면 아래의 명령어를 실행한다.
```
  git log
```

![git](/assets/images/monkey_1_gitinit_7.png)

가장 마지막에 작성된 "설명글 추가" 라는 이름의 커밋이 HEAD이다.
우리는 HEAD에서 이전 커밋으로 되돌아 갈 것이다.

원하는 커밋으로 이동하기 위해선 커밋 고유의 ID를 알아야한다. 커밋 고유 아이디는 위의 이미지에 노란색 글자로 나와 있는
"commit a4c086b~" 부분이다.

되돌아가려는 커밋의 앞 7자리나 전체를 복사하고 checkout 명령어로 해당 커밋으로 소스코드를 되돌린다.
```
  git checkout e1e2f23
```

커밋 이동에 성공했다면 다음과 같은 텍스트가 보인다.
![git](/assets/images/monkey_1_gitinit_8.png)

커밋이 이동 됐으니 결과를 확인해보자.

![git](/assets/images/monkey_1_gitinit_9.png)

성공적으로 커밋 이동 됐다. 이제 다시 최신 코드로 이동하고 싶다. 이동 방법은 아래와 같다

```
  git checkout -
```

최신 커밋으로 이동할 때는 커밋 고유 ID를 입력해도 되지만 '-'를 적어도 된다.

