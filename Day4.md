2020.01.20

# Git



__(분산) 버전 관리 시스템__

코드의 History를 관리하는 도구. 개발된 과정과 역사를 볼 수 있으며, 프로젝트의 이전 버전을 복원하고 변경 사항을 비교 분석 및 병합도 가능

ex) Bitbucket, BitLab, GitHub

* 터미널에서만은 동작할 수 없다. UL click으로 작업가능
* 차이가 무엇이고 수정 이유를 log로 남길 수 있다.
* 과거로 복원 가능 (왔다갔다 가능)\

~~~
					add  					commit			push : 		basic route

Working directory ---->	INDEX(staginf area) --->	HEAD 	--->	 Github
(작업(수정)한 파일) 			커밋할 목록			쌓인 커밋들
~~~

#### git의 기본

* log : history를 commit log로 남기면 뭔지 알 수 있다.

~~~
$git helloworld.py
~~~

#### git 초기화

```
1.$git config --global --unset ...
2.자격 증명 관리에서 수정or삭제 -> 초기화
3.$git credential reject
```



***

## CLI (Command Line Interface : 명령 줄 인터페이스)

#### CLI 종류

__1.유닉스 shell (유닉스 기반의 shell, bash)__

2.CP/M

3.DOS의 command.com

4.cmd(window 전용)



#### bash의 명령어 기초

* ls : 현재 디렉토리의 내용들을 나열

* cd : 현재 작업 디렉토리 변경

* mkdir : 새로운 디렉토리 생성

* echo : 문자열 출력

* rm : 파일 지우기

* exit : 터미널 종료

  

#### CLI에서는 항상 자신이 어디에 있는지 주의하자!!!

***

```
$git init : 해당폴더를 우리가 관리하겠다(master) --> 파일가서 숨긴 항목 보기하면 .git폴더 나타남
$git status : 현상태 확인
$git touch : 파일 만들기 ex) $ touch a.txt

Git 에 올리기
$git add a.txt (git status로 확인해보기)
($git rm --cached a.txt하면 파일 내려감)
$git commit -m "첫번째 커밋"
$git remote add origin https://github.com/seunghee6022/git_basic.git : 새로운 repository에  등록하겠다
$git remote -v
$git push -u origin master -> 두번째부터는 -u는 필요없다
```

`shift` + `insert` =붙여넣기



 [![](C:\Users\multicampus\Desktop\Markdown 필기\1.PNG)]

```
$git add . :현재 파일에 있는 모든 폴더들을 올리겠다.
$git commit -m "내용 아무거나"
$git push origin master
```

* origin  이름 변경하기

  ```
  $git remote rename origin(현 설정된 이름) shj622(바꾸고 싶은 이름)
  ```

* 저장한것 불러오기

```
$git clone 저장소 주소
$ git clone https://github.com/seunghee6022/git_basic.git 최초 한번만 클론으로 땡기고 나머지는 pull로 가져오면 된다,
$ git remote -v
```

* home에도 ssafy파일에서 저장한거 불러오기 

__push가 안될 때에는 pull먼저 하고 한다!!!!__

```
$git remote add origin(repository 등록먼저)
$git remote -v
$git pull origin master ->b.txt 불러와짐
```

* pull 없이 작업할 때 생기는 문제점

c.txt를 ssafy폴더에서 push했는데 home폴더에서도 push하려하면 이력이 달라서 push가 되지 않는다. 이럴 땐 pull먼저 한 후

![](C:\Users\multicampus\Desktop\Markdown 필기\3.PNG)

이게 뜨면 `Esc`+`:`+`q` 하면 나갈 수 있고 

그다음에 push를 다시 하면 된다.



* 저장소에 올리고 싶지 않은 파일이 있을 때 (gitignore)

```
$touch .gitignore ->이름없는 txt파일 생성됨
```

gitignore을 open code로 열어서 secret.txt라고 친다.

->저장소

![](C:\Users\multicampus\Desktop\Markdown 필기\1-1579487488460.PNG)

secret.txt는 보이지 않고 .gitignore만 보이는 것을 알 수 있다.

***

### 어떤 파일이 올라가면 안되는지 모를 떄 활용 사이트

### gitignore.io

![](C:\Users\multicampus\Desktop\Markdown 필기\1-1579487847931.PNG)

내용들을 다 복붙해다가 python open code열려있는 곳에 복붙

![](C:\Users\multicampus\Desktop\Markdown 필기\1-1579487934823.PNG)