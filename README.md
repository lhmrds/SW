## TOP 명령어
**리눅스 시스템의 CPU 사용량, 메모리 사용량 등 전반적인 상황을 실시간으로 모니터링할 수 있는 명령어**

`top [option]`

### 요약 영역
- 전체 프로세스가 OS에 대해서 리소스를 어느 정도 차지하고 있는지를 알려줌

![image](https://blog.kakaocdn.net/dn/cIwHTf/btqYiCOXiQk/0wpKbRc7uKG8mo9vfKLWiK/img.png)

#### 1. 시스템 시간, Uptime, 유저 세션 수
| System time, uptime, user sessions |
|---|
- 각 시스템의 현재 시간, OS가 얼마나 살아있는지, 현재 접속 중인 유저 세션 수를 나타냄

#### 2. 로드 애버리지
| Load Average |
|---|
- CPU Load의 이동 평균을 표시함

#### 3. Tasks
| Tasks |
|---|
- 현재 프로세스들의 상태를 나타냄

#### 4. CPU 사용량
| CPU |
|---|
- CPU가 어떻게 사용되고 있는지 사용률을 보여줌

#### 5. 메모리 사용량
| Memory |
|---|
- Mem: RAM의 정보를 출력함
- Swap: 스크를 메모리처럼 사용하여 정보를 출력함
- total: 총 메모리 양
- free: 사용 가능한 메모리 양
- used: 사용 중인 메모리 양
- buff/cache: IO와 관련되어 사용되는 버퍼에 사용되는 메모리
- avail Mem: swap 메모리를 사용하지 않고 사용할 수 있는 메모리의 크기

#### 6. 디테일 영역
- PID: 프로세스 ID
- USER: 프로세스를 시작한 유효한 사용자의  ID
- PR : 커널에 의해 스케줄링되는 우선순위
- NI : 우선순위에 영향을 주는 값
- VIRT : 프로세스가 사용하고 있는 가상메모리 용량
- RES : 프로세스가 실제로 사용하고 있는 물리 메모리 용량
- SHR : 다른 프로세스와 공유하고 있는 공유 메모리 용량
- S : 프로세스의 상태
  - R : Runnung
  - S : Sleeping
  - I : Idle
  - D : Uninterruptable Sleep
  - T : 작업 제어 신호에 의해 중지됨
  - t : Trace 중 디버거에 의해 중지됨
  - Z : Zombie
- %CPU : CPU 사용량
- %MEM : 현재 사용한 실제 메모리 양
- TIME+ : 작업이 시작된 이후 사용한 총 CPU 시간
- COMMAND : 작업을 시작할 때 사용되는 명령어 라인 혹은 프로그램의 이름을 표시

--------------------

## PS 명령어
**현재 실행 중인 프로세스와 상태를 출력하는 명령어**

`ps [option]`

<img width="248" alt="스크린샷 2024-06-02 014900" src="https://github.com/lhmrds/SW/assets/165414907/75e7d8c1-ef77-45b1-8cc4-93a225a6a23b">

### 명령어 옵션
| 옵션 | 의미 | 
|:---:|:---|
|-A | 모든 프로세스를 출력 |
|a (BSD) | 터미널과 연관된 프로세스를 출력, x 옵션과 같이 사용하여 모든 프로세스를 출력할 때 사용 |
|-a | 세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력 |
|-e | 커널 프로세스를 제외한 모든 프로세스를 출력 |
|-f | 출력을 풀 포맷으로 표기, UID, PID , PPID 등이 함께 표시 |
|-l (System V) | 출력을 긴 포맷으로 표기 |
|l (BSD) | 프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI 값과 NI 값을 확인 |
|-o | 출력 포맷을 지정 |
|-M | 64비트 프로세스들을 출력 |
|-m | 프로세스뿐만 아니라 커널 스레드도 출력 |
|-p | 특정 PID를 지정하여 출력 |
|-r | 현재 실행 중인 프로세스 출력 |
|u (BSD) | 프로세스의 소유자를 기준으로 출력 |
|-u [사용자] | 특정 사용자의 프로세스 정보를 출력, 사용자를 지정하지 않는다면 현재 사용자 기준으로 출력 |
|x (BSD) | 데몬 프로세스처럼 터미널에 종속되지 않은 프로세스를 출력 |
|-x | 로그인 상태에 있는 동안 아직 완료되지 않은 프로세스를 출력 |

### 명령어 출력 항목
| 필드 | 의미 | 
|:---:|:---|
|USER (BSD), UID (System V) | 프로세스 소유자의 이름 |
|PID | 프로세스의 식별 번호 |
|PPID | 부모 프로세스의 PID |
|%CPU | CPU 사용 비율의 추정치 (BSD) |
|%MEM | Memory 사용 비율의 추정치(BSD) |
|VSZ | KiB 단위 또는 페이지 단위의 가상 메모리 사용량 |
|RSS | 실제 메모리 사용량 |
|TTY | 프로세스와 연결된 터미널 |
|S (System V), STAT (BSD) | 현재 프로세스의 상태 코드 |
|TIME | 총 CPU 사용 시간 |
|COMMAND | 프로세스의 실행 명령행 |
|STIME | 프로세스가 시작된 시간 혹은 날짜 |
|C (System V), CP (BSD) | 짧은 기간 동안의 CPU 사용률 |
|F | 플래그 |
|PRI | 실제 실행 우선순위 |
|NI | nice 우선순위 번호 |

--------------------

## JOBS 명령어
**백그라운드로 실행된 프로그램이나 "Ctrl + z"를 입력하여 실행한 프로그램에 대해서 확인하는 명령어**

`jobs [option]`

<img width="414" alt="스크린샷 2024-06-02 015731" src="https://github.com/lhmrds/SW/assets/165414907/5348d743-5c4a-4e4d-8645-ad28a5210f47">

### 명령어 옵션
| 옵션 | 의미 | 
|:---:|:---|
|-p	| 백그라운드에 있는 프로세스의 프로세스 아이디(PID)만 출력 |
|-l	| 백그라운드에 있는 프로세스의 프로세스 아이디(PID)를 함께 출력 |
|-s	| 백그라운드에 있는 프로세스 중 멈춰 있는 프로세스만 출력 |
|-r	| 백그라운드에 있는 프로세스 중 실행 중인 프로세스만 출력 |

### 백그라운드 작업의 상태값
| 상태 | 의미 | 
|:---:|:---|
|Running | 작업이 계속 진행 중 |
|Done | 작업이 완료되어 0을 반환 |
|Done (code) | 작업이 종료되었으며 0이 아닌 코드를 반환 |
|Stopped | 작업 일시 중단 |

--------------------

## KILL 명령어
**프로세스를 종료하는 명령어**

`kill [option] <PID>`

<img width="517" alt="스크린샷 2024-06-02 021723" src="https://github.com/lhmrds/SW/assets/165414907/53217e68-9f8f-42d6-beeb-3f303cc3bf45">

### 명령어 옵션
| 옵션 | 의미 |
|:---:|:---|
|-s <signal> | 특정 시그널(signal)을 사용하여 프로세스를 종료, 기본적으로 SIGTERM 시그널 사용 |
|-l, --list | 지원되는 시그널(signal) 목록을 출력 |
|-a, --all | 현재 사용자에 속한 모든 프로세스를 종료 |
|-q, --queue | 프로세스에 시그널을 보내는 대신 시그널을 대기열에 추가 |
|-9 [PID] | 프로세스 아이디(PID)를 직접 지정하여 프로세스를 강제로 종료 |
###### ※ `kill -9 <PID>` : 프로세스를 멈추는 가장 강력한 방법이지만 데이터 손실이 발생할 수 있음!

### -l 명령어 옵션 시 사용 가능한 신호
| 번호 | 신호 이름 | 신호 | 의미 |
|:---:|:---:|:---:|:---|
|1 |SIGHUP |HUP | hangup, 로그아웃등의 접속이 끊을 때 발생하는 신호로, 특정 실행 중인 프로그램이 사용하는 설정 파일을 변경시키고 변화된 내용을 적용할 때 사용 |
|2 |SIGINT	|INT | 현재 작동중인 프로그램의 동작을 멈출때 사용되며, 일반적인 값은 <CTRL>+<c> |
|9 |SIGKILL |KILL | 프로그램을 무조건 종료할 경우 사용 |
|11 |SIGSEGV |SEGV | 잘못된 메모리 관리시 생기는 신호 |
|15 |SIGTERM |TERM | 실행 중인 프로그램을 정상적인 종료 방법으로 프로그램을 종료하는 신호(Signal)로, kill 명령에서 신호를 지정하지 않으면 이 신호를 사용하여 프로그램을 종료 |
|18 |SIGCONT |CONT | 중지되어 있는 프로그램을 재실행하는 데 사용되는 신호 |
|19 |SIGSTOP |STOP | 프로그램을 중지하는 데 사용되는 신호 |
|20 |SIGTSTP |TSTP |터미널에서 중지되어 있는 신호 |

### 명령어 장단점
- 장점
  - 간단한 명령어로 빠르게 프로세스를 종료할 수 있음
  - 다양한 옵션을 사용하여 프로세스 동작을 제어할 수 있음
- 단점
  - 잘못 사용하면 의도치 않은 프로세스 종료가 발생할 수 있음
  - SIGKILL 시그널을 사용하여 강제 종료할 경우, 프로세스가 올바르게 정리되지 않을 수 있고, 데이터 손실 등의 문제가 발생할 수 있음
