---
title: "원숭이도 따라하는 Git & GitHub (2)"
excerpt: "원숭이도 따라하는 시리즈 깃허브 두 번째 포스트"
toc: true
toc_sticky: true

categories:
  - Git
tags:
  - Git
  - Github
last_modified_at: 2022-01-31T18:36:00
---

저번 포스터에 이어 원격저장소에 새로운 커밋을 로컬저장소에 갱신하는 방법에 대해 공부 할 것이다. work-B 로컬 저장소에서 작업한 내용을 원격저장소에 업로드 하고 work-B에 해당 내용을 갱신해 볼 것이다.

### **작업 폴더 구성하기**
개발 프로젝트에 팀원 A, 팀원 B가 있다고 했을 때 원격저장소에 있는 소스코드를 내려 받아 작업 하려 한다.
그때 사용하는 것이 clone 이다.

1. 기존에 작업하던 폴더의 이름을 work-B라고 바꿔준다.

2. work-B라는 폴더 생성 후 폴더 안으로 이동하여 마우스 우클릭을 한다. 깃이 PC에 깔려 있다면 Git Bash Here이 보일 것이다. 클릭하여 git bash를 열고 아래와 같은 명령어를 실행한다.

```
    git clone "원격저장소 주소"

    또는 

    git clone "원격저장소 주소" .
```

첫번째 clone 방식은 원격저장소의 내용이 새로운 폴더에 생성되고, 두번째 방식은 폴더 생성 없이 내용만 가져온다. 

![git](/assets/images/monkey_1_gitinit_10.png)

clone에 성공했다면 위와 같은 메시지가 나온다.

다음과 같이 폴더를 구성 해준다.

![git](/assets/images/monkey_1_gitinit_11.png)<br>
work-A는 원격저장소에 Push한 최종 소스코드가 있는 곳이고 work-B는 원격저장소에서 Clone 받은 파일이다.
현재 두 소스코드의 버전과 내용은 동일하다. 이제 work-B를 수정하여 원격저장소에 Push할 것이다.

```
    원숭이도 따라하는 깃허브 
    work-B 업로드
```
위와 같이 work-B 폴더의 README.txt 파일을 수정한다.

```
    git add *
    git commit -m "work-B 작업"
    git push origin master
```
다음과 같이 원격저장소에 README.txt 파일이 변경된 것을 확인한다.

![git](/assets/images/monkey_1_gitinit_12.png)

이로써 work-A와 work-B의 버전과 내용이 달라졌다. 이제 work-A에 원격저장소의 내용을 받아오고 싶다.
아래와 같이 입력한다.

### **원격 저장소에 있는 내용으로 갱신하기** 

```
    git pull origin master
```

원격저장소의 내용이 반영된 README.txt 파일을 확인해본다.
![git](/assets/images/monkey_1_gitinit_13.png)

work-A에는 원격저장소에 업로드한 HEAD 커밋과 로컬 저장소에서 수정한 내용과
원격저장소에서 Pull 하여 내려받은 저장소 내용이 모두 합쳐졌다.

```
원숭이도 따라하는 깃허브
<<<<<<< HEAD 
//원격저장소에 업로드한 커밋

아무리 쉽게 써도 진짜 원숭이가 따라 할 순 없겠지...  
//로컬 저장소에서 추가한 내용

=======
work-B 업로드
>>>>>>> 3f21cc52e334d0ed6d4e56c99bf19ec5bb36b91a
// 원격저장소에서 내려받은 커밋
```
