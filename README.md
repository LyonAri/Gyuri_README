### 오픈소스 SW 개론
## 리눅스 명령어 및 vim 에디터 매크로 사용방법 정리
#### 20213069 박규리
---
* # 리눅스 명령어

>## 1. top 명령어
>
>* top 명령어는 table of processes 의 약자
>* 유닉스 계열의 시스템에서 프로세스 목록을 CPU 사용률이 높은 것부터 보여줌
>* 시스템의 프로세스와 메모리 사용상태를 5초의 간격으로 업데이트 하여 화면에 출력
>
>>* #### top 명령어 실행화면
>>
>>![unknown](https://user-images.githubusercontent.com/106807456/171993354-07add5cf-1795-43cc-803e-1b154d7f19ed.png)
>>
>>top - 18:20:37 : 현재 서버의 시간
>>
>>up 2:49 : 서버의 구동 시간 (2시간 49분째)
>>
>>users : 접속중인 유저 세션 수
>>
>>load average : 부하율, 좌측부터 1분, 5분, 15분에 대한 평균값
>>
>>Tasks total : 전체 프로세스 개수
>>
>>running : 실행중인 프로세스 개수
>>
>>sleeping : 대기중인 프로세스 개수
>>
>>stopped : 종료된 프로세스 개수
>>
>>zombie : 좀비상태인 프로세스 개수
>>
>>us : 프로세스의 유저 영역에서의 CPU 사용률
>>
>>sy : 프로세스의 커널 영역에서의 CPU 사용률
>>
>>ni : 프로세스의 우선순위(priority) 설정에 사용하는 CPU 사용률
>>
>>id : 사용하고 있지 않는 비율
>>
>>wa : IO가 완료될때까지 기다리고 있는 CPU 비율
>>
>>hi : 하드웨어 인터럽트에 사용되는 CPU 사용률
>>
>>si : 소프트웨어 인터럽트에 사용되는 CPU 사용률
>>
>>st : CPU를 VM에서 사용하여 대기하는 CPU 비율
>
>>* #### top 실행 후 명령어
>>
>>|입력키|설명|
>>|---|---|
>>|shift+p|CPU 사용률이 높은 프로세스 순서대로 표시|
>>|shift+m|메모리 사용률이 높은 프로세스 순서대로 표시|
>>|shift+t|프로세스가 돌아가고 있는 시간 순서대로 표시|
>>|k|프로세스  kill  - k 입력 후 종료할 PID 입력 signal을 입력하라고 하면 kill signal인 9를 입력|
>>|a|메모리 사용량에 따라 정렬|
>>|b|Batch 모드 작동|
>>|c|명령행/프로그램 이름 토글|
>>|d|지연 시간 간격은 다음과 같다. -d ss. tt (seconds.tenths)|
>>|h|도움말|
>>|1|CPU Core별로 사용량 보여줌|


>## 2. ps 명령어
>* ps 명령어는 process status 의 약자
>* 현재 실행중인 프로세스 목록과 상태를 보여줌(윈도우의 작업관리자)
>
>>* #### ps 명령어 실행화면(옵션 X)
>>![unknown (1)](https://user-images.githubusercontent.com/106807456/171994644-d2e90a5c-467e-488f-bfcb-dedca66eeaa6.png)
>>
>>PID : (일시적인)프로세스 번호
>>
>>TTY : 터미널 번호
>>
>>TIME : 해당 프로세스가 사용한 CPU의 시간
>>
>>CMD : 프로세스가 실행중인 명령
>
>>* #### ps 주요옵션
>>
>>![unknown (2)](https://user-images.githubusercontent.com/106807456/171994923-a7f839b0-39b4-492d-b321-3b0cf14c5279.png)
>>
>>|옵션|설명|
>>|---|---|
>>|-e|모든 프로세스를 출력해준다.|
>>|-f|풀 포맷으로 보여준다.(UID, PID 등)|
>>|-l|긴 포맷으로 보여준다.|
>>|p, -p|특정 PID의 프로세스를 보여준다.|
>>|-u|특정 사용자의 프로세스를 보여준다.|


>## 3. jobs 명령어
>* 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경 되었지만 보고되지 않은 상태 등을 표시하는 명령어
>
>>* #### jobs 상태값
>>|상태|설명|
>>|---|---|
>>|Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임을 뜻한다.|
>>|Done|작업이 완료되어 0을 반환하고 종료했음을 뜻한다.|
>>|Done(code)|작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환했음을 뜻한다|
>>|Stopped|작업이 일시 중단됨을 뜻한다.|
>>|Stopped(SIGTSTP)|SIGTSTP 신호가 작업을 일시 중단했음을 뜻한다.|
>>|Stopped(SIGTOP)|SIGSTOP 신호가 일시 중단했음을 뜻한다.|
>>|Stopped(SIGTTIN)|SIGTTIN 신호가 작업을 일시 중단했음을 뜻한다.|
>>|Stopped(SIGTTOU)|SIGTTOU 신호가 작업을 일시 중단했음을 뜻한다.|
>
>>* #### jobs 주요옵션
>>
>>|옵션|설명|
>>|---|---|
>>|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
>>|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
>>|-p|각 프로세스 ID에 대해 한 행씩 출력|
>>|command|지정한 명령어를 실행|


>## 4. kill 명령어
>* 프로세스에 특정한 signal을 보내는 명령어
>* 일반적으로 종료되지 않는 프로세스를 종료 시킬 때 많이 사용함
>
>>* #### kill 옵션
>>
>>![unknown (3)](https://user-images.githubusercontent.com/106807456/171997929-d3fc1de0-e627-48a2-b140-6304771050a3.png)
>>
>>|옵션|설명|
>>|---|---|
>>|-l|signal의 종류를 출력한다.|
>
>>* #### 주요 signal
>>
>> 1 ) SIGHUP : 세션이 종료될 때 시스템이 내리는 시그널
>> 
>> 2 ) SIGINT : Ctrl + C, 종료 요청 시그널
>> 
>> 9 ) SIGKILL : 강제 종료 시그널
>> 
>> 11 ) SIGSEGV : 메모리 침범이 일어날 때 시스템이 보내는 시그널
>> 
>> 15 ) SIGTERM : 기본 값, 종료 요청 시그널
>> 
>> 20 ) SIGTSTP : Ctrl + Z 일시 중지 요청 시그널
---
* # vim 에디터
## 매크로 사용방법(q)
* 매크로 : 특장한 움직임 또는 입력을 키에 저장함으로써 단순하면서 반복되는 동작을 쉽고 빠르게 해주는 것

1. 초기 vim 에디터 화면
![unknown (4)](https://user-images.githubusercontent.com/106807456/171999281-9c7669e7-66cb-4c02-920a-3fc041e48c26.png)

2. q + [매크로 이름]을 입력 (recording 시작)
![unknown (5)](https://user-images.githubusercontent.com/106807456/171998707-9ba773d9-7638-4481-87e0-801a3e4aee9c.png)
(실행화면의 매크로 이름 = a)

3. 내가 반복하길 원하는 동작 및 키 입력
![unknown (6)](https://user-images.githubusercontent.com/106807456/171998758-3a5f77fd-55fb-4734-86d7-9fcb37105322.png)

4. q 입력 (recording 종료)
![unknown (7)](https://user-images.githubusercontent.com/106807456/171998801-b8135ea1-966b-4f6e-9b95-0339eca87846.png)

5. @ + [매크로 이름]을 입력
![unknown (8)](https://user-images.githubusercontent.com/106807456/171998852-93643fb8-80e1-40bf-b595-572b313129de.png)

6. @@ 입력으로 방금 실행한 매크로 실행
![unknown (9)](https://user-images.githubusercontent.com/106807456/171998886-1f939890-0a3d-4d7b-8673-e6f8fbed680d.png)

7. [실행하고 싶은 횟수] + @ + [매크로 이름]
![unknown (10)](https://user-images.githubusercontent.com/106807456/171999032-ea1137b9-464a-4400-9f42-82c42535f88b.png)
(실행화면 = 5@a : 매크로 a를 5회 실행)
