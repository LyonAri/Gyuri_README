### 오픈소스 SW 개론
## 리눅스 명령어 및 vim 에디터 매크로 정리
#### 20213069 박규리
---
* 리눅스 명령어

>## 1. top 명령어
>
>* top 명령어는 table of processes 의 약자
>* 유닉스 계열의 시스템에서 프로세스 목록을 CPU 사용률이 높은 것부터 보여줌
>* 시스템의 프로세스와 메모리 사용상태를 5초의 간격으로 업데이트 하여 화면에 출력
>
>>![unknown](https://user-images.githubusercontent.com/106807456/171993354-07add5cf-1795-43cc-803e-1b154d7f19ed.png)
>>
>>#### top 명령어 실행화면
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

>#### top 실행 후 명령어
>
>|입력키|설명|
>|---|---|
>|shift+p|CPU 사용률이 높은 프로세스 순서대로 표시|
>|shift+m|메모리 사용률이 높은 프로세스 순서대로 표시|
>|shift+t|프로세스가 돌아가고 있는 시간 순서대로 표시|
>|k|프로세스  kill  - k 입력 후 종료할 PID 입력 signal을 입력하라고 하면 kill signal인 9를 입력|
>|a|메모리 사용량에 따라 정렬|
>|b|Batch 모드 작동|
>|c|명령행/프로그램 이름 토글|
>|d|지연 시간 간격은 다음과 같다. -d ss. tt (seconds.tenths)|
>|h|도움말|
>|1|CPU Core별로 사용량 보여줌|

>## 2. ps 명령어
