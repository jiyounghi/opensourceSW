# 20204424 문지영 오픈소스SW 과제



## 리눅스 명령어
| 명령어 |설명|활용|
|----|-----|---|
|```top```|실시간으로 CPU 사용률 체크해주는 명령어.|```$ top```|
|```ps```|현재 실행중인 프로세스의 목록을 보여주는 명령어이다.|```$ ps -ef```|
|```jobs```|현재 쉘 세션에서 실행시킨 백그라운드 작업의 목록이 출력되는 명령어이다.|```$ jobs```|
|```kill```|안전하게 종료하기 위해 프로세스에 시그널을 보내는 명령어이다.|```$ kill [process name]```|


---
### top
#### *top 명령어란?*
- 유닉스계열 시스템에서 프로세스 목록을 CPU 사용률이 높은 것부터 보여주는 소프트웨어

top 명령어는 줄 순서대로 표현한다고 보면 된다.
1. 로드 에버리지 (Load Average)
2. Tasks
3. CPU 사용량
4. 메모리 사용량
5. 디테일 영역

#### 사용 방법 
|옵션|설명|
|---|---|
|-b|배치모드로 정보 일렬로 출력. 실시간 상화 대화형모드|
|-d delay|지정한 시간의 간격으로 정보를 업데이트하여 출력|
|-i idle|토글값이 off일 때, idle 프로세스나 좀비 프로세스 정보 출력 안함|
|-n num|지정한 시간만큼 업데이트 정보 출력|
|-p pid|지정한 프로세스 ID(pid)의 정보만 출력|
|-q|시간 간격없이 멈추지않고 업데이트 정보 출력|
|-s|몇 개의 대화식 명령을 비활성화|
|-S|누적된 정보 출력|


---
### ps
#### ps 명령어란?
- 현재 실행중인 프로세스 목록을 보는 명령어이다. 
- ps -ef , ps aux 를 많이 사용한다. 
#### 사용 방법 
|옵션|설명|
|---|---|
|-A|터미널과 연관된 프로세스를 출력|
|-a|세션 리더를 제외하고 터미널에 종속되지 않은 모든 프로세스 출력|
|-e|커널 프로세스 제외하고 모든 프로세스 출력|
|-f|유닉스 스타일로 풀 포맷으로 출력|
|-o|출력 포맷 지정하는 옵션 (pid, tty, time, cmd 등)|
|-M|64비트 프로세스 출력|
|-m|프로세스, 커널 스레드 출력|
|-p|특정 PID 지정할때 사용|


---
### jobs
#### jobs 명령어란? 
- 백그라운드로 실행되는 작업목록이 출력되는 리눅스 명령어
- 각 작업에는 번호가 붙어있다. 
- 현재 쉘 프로세스(bash)의 자식 백그라운드 프로세스들을 보여준다고 할 수 있다.

#### 사용방법
|옵션|설명|
|---|---|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

#### ※jobs로 출력되는 작업의 상태 값
|상태|설명|
|---|---|
|Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임|
|Done|작업이 완료되어 0을 반환하고 종료 되었음|
|Done(code)|작업이 정삭적으로 완료되어 종료되었고, 0이 아닌 코드를 반환 했음을 의미|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 신호가 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 신호가 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 신호가 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 신호가 작업을 일시 중단|


---
### kill 
### kill 명령어란?
- 안전하게 종료하기 위해 프로세스에 시그널을 보내는 명령어이다. 
- 주로 SIGKILL 시그널에 쓰인다. 일반적인 상황에서는 SIGKILL을 사용하면 데이터 유실 같은 문제가 발생할 수 있기 때문에 추천하지 않는다.

#### 사용 방법
`kill [-옵션 or 시그널] PID` 
|옵션|설명|
|---|---|
|-l|signal 종류 출력|


---
## vim 매크로 사용법
#### 매크로란 같은 동장을 반복하게 해줌
*+ 매크로 기록하는 방법*
+ 1) 중립모드
+ 2) q 누른 후 알파벳 입력해줌으로 매크로 이름 지정
+ 3) --recording--이 뜨면 기록할 것 입력
+ 4) 입력 끝나면 q 누르기

*+매크로 재생하는 방법*
+ 1) 중립모드
+ 2) @ 누른 후 매크로이름 입력한다.
+ 3) 매크로 재생됨 
+ 4) @@ 누르면 제일 마지막에 재생된 매크로 재생 

*+매크로를 파일로 저장하는 방법*
+ 1) ~/.vimrc 파일 열기 
+ 2) let @<매크로이름>=' 생성
+ 3) insert 모드 
+ 4) Ctrl+r Ctrl+r <매크로 이름> 입력하면 <매크로 이름>의 내용물 입력됨
+ 5) ' 를 입력 후 마침 
