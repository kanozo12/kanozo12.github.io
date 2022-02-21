---
title: "원숭이도 따라하는 Git & GitHub (1) - 개념 및 환경 구축"
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

이 포스트는 [원숭이도 따라하는 Git & GitHub 시리즈](/monkey/)의 첫 번째 포스트이다.
Git 과 GitHub가 무엇인지 알아 보기 앞서 버전관리가 무엇인지 부터 알아볼 것이다.

### **버전관리**

팀 프로젝트에서 사용할 공용폴더를 만들고 그곳에 소스코드를 올린다고 가정했을 때,
이곳에 올려진 소스코드를 "Test 버전 00"이라고 정하겠다.
팀원 Jack이 "Test 버전"의 소스코드를 수정해 "수정 버전 01"으로 저장하고 팀원 Beer가 "수정 버전 01"을 수정하여 "최종 버전 02"으로 저장 할 수 있을 것이다. <br><br>
이와 같이 최종 버전을 기준으로 수정하고 순차적으로 번호를 붙여 저장하면 버전관리가 될 것이다. 그런데 팀원 Jack과 Beer가 동시에 "수정 버전 01"을 수정해서 "수정 버전 02"로 저장 한다면 어떻게 될까, 이처럼 협업이 필요한 개발작업에선 버전관리가 필수이다. 

### **Git? GitHub?**
앞서 설명한 버전관리라는 작업을 가능하게 해주는 시스템이 바로 Git 이다. 전세계적으로 수 많은 개발자가 Git으로
협업과 버전관리를 진행하고 있다. Git은 데이터를 저장할 공간만 있다면 어디서든 사용 가능하다. USB나 HDD와 같은
휴대용 저장공간에서 Git을 사용한다면 어디서든 내가 작업하고 있는 프로젝트를 사용 가능할 것이다. 

만약 클라우드 환경에
Git을 올려둔다면 팀 프로젝트를 하는 다른 팀원들과 함께 버전 관리가 가능할 것이다.

이와 같이 Git으로 관리하는 프로젝트를 업로드 할 수 있는 Git 호스팅 사이트 중 하나가 대표적으로 GitHub인 셈이다. 
GitHub 이외에 GitLab, BitButcket 등 다양하다. 
Github에 소스코드를 올려두면 시간, 공간 제약없이 협업 할 수 있다

### **GitHub 가입하기**
깃허브를 사용하기 앞서 가입 방법 부터 알아보겠다.

  1. GitHub 사이트 [깃허브 주소](https://www.GitHub.com/)에 접속해서 우측 상단의 [Sign Up] 버튼을 클릭한다.
  ![git](/assets/images/monkey_1_gitinit_14.png)

  2. GitHub에 사용할 본인 이메일을 입력해 준다.
  ![git](/assets/images/monkey_1_gitinit_15.png)
    다음과 같이 입력후 continue 버튼을 눌러준다.

  3. 입력한 메일에 인증 코드가 오면 입력후 Enter를 눌러준다.
  ![git](/assets/images/monkey_1_gitinit_16.png)

  4. 다음과 같은 화면이 나타나면 GitHub를 사용할 준비가 모두 끝났다.
  ![git](/assets/images/monkey_1_gitinit_17.png)


### **컴퓨터에 Git 설치하기**
앞에서 가입한 GitHub에 업로드할 소스코드를 관리하기 위한 Tool 인 Git을 설치한다.

1. GitHub 사이트 [깃 홈페이지 주소](https://git-scm.com/downloads)에 접속해서 [Download] 버튼을 클릭한다.
![git](/assets/images/monkey_1_gitinit_18.png)

2. 다운받은 설치파일을 실행 후 다른 설정은 건드리지 말고 모두 Next와 같은 긍정적인 답변으로 일관한다.

3. 설치가 다 끝나면 설치 확인을 위해 윈도우 검색으로 [Git Bash]를 검색한다.

4. 검정색 창이 뜰텐데 명령어 입력란에 [git] 이라는 명령어를 입력한다.

5. 다음과 같은 결과가 나오면 성공적으로 Git이 설치된 것이다.
![git](/assets/images/monkey_1_gitinit_19.png)

