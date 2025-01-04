# Operation System

## 운영체제 개요

#### 운영체제의 역할과 목적
- 정의: 
  - 프로그램에 필요한 자원을 할당하고, 프로그램이 올바르게 실행되도록 돕는 특별한 소프트웨어.
- 역할:
  - 자원 관리
  - 프로세스 관리
  - 메모리 관리
  - 파일 시스템 관리
  - 사용자 인터페이스 제공
  - I/O 장치 관리
- 목적:
  - 유저 프로그램의 실행 및 문제 해결
  - 효율적인 방법으로 하드웨어 사용
  - 컴퓨터 시스템의 편리한 이용

#### 운영체제의 구조 (Structure of Operating Systems)
![image](/image/os_structure.png)
- 특징:
  - 크게 User interface, System call, service 부분으로 나뉜다.
  - User interface 부분은 GUI, batch 파일, Shell이 포함된다.
  - System call 부분은 Kernel mode로 작동하는 명령어를 수행하는 부분이다.
  - Service 부분은 프로그램 개발 및 실행에 편리한 환경을 제공한다.

##### 커널(Kernel)
- 정의:
  - 
##### 사용자 모드(User Mode) vs 커널 모드(Kernel Mode)

#### 운영체제의 종류 (Types of Operating Systems)

##### 단일 사용자/다중 사용자(Single-user/Multitasking)
##### 단일 작업/다중 작업(Single-tasking/Multitasking)
##### 분산 OS(Distributed Operating Systems)
##### 실시간 OS(Real-Time Operating Systems)


## 프로세스 관리 (Process Management)//ch3
#### 프로세스와 스레드 (Processes and Threads)
##### 프로세스 상태(Process States) - 생성(New), 준비(Ready), 실행(Running), 대기(Waiting), 종료(Terminated)
##### 스레드(Thread) - 멀티스레딩(Multithreading)의 개념과 장점


#### CPU 스케줄링 (CPU Scheduling)//ch 5
##### 선점형 스케줄링 (Preemptive Scheduling) - SJF (Shortest Job First), Priority Scheduling, Round Robin 등
##### 비선점형 스케줄링 (Non-preemptive Scheduling) - FCFS (First-Come-First-Served), Priority Scheduling 등
##### 스케줄링 성능 평가 (응답 시간, 대기 시간, 처리량 등)


#### 동기화 (Synchronization)//ch3, ch6 ch 7
##### 임계 구역 문제 (Critical Section Problem)
##### 세마포어(Semaphore)와 모니터(Monitor)
##### 뮤텍스(Mutex)와 조건 변수(Condition Variables)


#### 교착상태 (Deadlock) //ch 8
##### 교착상태의 조건 (Conditions for Deadlock)
##### 교착상태 해결 방법 (Deadlock Handling) - 예방(Prevention), 회피(Avoidance), 탐지(Detection), 복구(Recovery)


## 메모리 관리 (Memory Management) //ch 9
#### 메모리 계층 구조 (Memory Hierarchy)
#### 주기억장치 관리 (Main Memory Management)
##### 단순 관리 (Simple Management) - 고정 분할(Fixed Partition), 가변 분할(Variable Partition)
##### 페이징(Paging)과 세그멘테이션(Segmentation)
##### 페이징과 세그멘테이션의 조합


#### 가상 메모리 (Virtual Memory) //ch10

##### 페이지 교체 알고리즘(Page Replacement Algorithms) - FIFO, LRU, Optimal

##### 스왑 공간 관리 (Swap Space Management)

## 파일 시스템 (File System) 
#### 파일의 개념과 구조 (Concept and Structure of Files)
#### 디렉토리 구조 (Directory Structure)
##### 단일 레벨(Single Level), 다중 레벨(Multi-Level), 트리 구조(Tree Structure)

#### 파일 할당 방법 (File Allocation Methods)
##### 연속 할당(Contiguous Allocation), 연결 할당(Linked Allocation), 색인 할당(Indexed Allocation)

#### 파일 시스템 구현 (File System Implementation)
##### 디스크 스케줄링 알고리즘 (Disk Scheduling Algorithms) - FCFS, SSTF, SCAN, C-SCAN 등
##### 파일 시스템 무결성 (File System Integrity) - 저널링(Journaling), RAID(Redundant Array of Independent Disks)

## 입출력 관리 (I/O Management)

#### I/O 하드웨어와 소프트웨어 (I/O Hardware and Software)
- 정의:
  - I/O 하드웨어는 컴퓨터 시스템이 외부와 상호작용할 수 있도록 하는 물리적 장치이다.
  - I/O 소프트웨어는 I/O 하드웨어를 제어하고, 데이터의 입출력을 관리하는 소프트웨어이다.
- 특징:
  ![image](/image/kernelio.png) 
  - I/O 하드웨어에는 입력 장치, 출력 장치, 저장 장치, 네트워크 장치가 있다.
  - I/O 소프트웨어는 장치 드라이버, I/O 관리 서브시스템, 파일 시스템이 있다.
  - Port, Bus, Controller를 통해서 하드웨어와 소프트웨어가 신호를 주고 받는다.
#### 장치 드라이버의 역할 (Role of Device Drivers)
- 정의:
  - 장치 컨트롤러의 동작을 감지하고 제어함으로써 장치 컨트롤러가 컴퓨터 내부와 정보를 주고받을 수 있게 하는 프로그램이다.
- 역할:
  - 하드웨어와의 통신
  - 장치 초기화 및 설정
  - 데이터 전송 관리
  - 장치 상태 모니터링

#### 인터럽트와 폴링 (Interrupts and Polling)
1. 인터럽트(Interrupts)
- 정의:
  - 인터럽트란 I/O 장치가 CPU에 데이터를 전송할 준비가 되었을 때, 또는 특정 이벤트가 발생했을 때 CPU에게 알리는 방식이다.
- 특징:
  - 비동기식 통신으로 장치가 준비되면 CPU에 신호를 보내, CPU가 현재 작업을 중단하고 장치의 요청을 기다린다.
  - CPU는 I/O의 작업을 기다리지 않고, 다른 작업 수행 가능하다.
- 처리 과정:
  ![image](/image/interruptio.png) 
  1. I/O 장치가 데이터를 전송할 준비가 되면 인터럽트를 발생시킨다.
  2. CPU는 현재 실행 중인 작업을 중단하고, 인터럽트 처리 루틴으로 전환한다.
  3. CPU는 인터럽트 서비스 루틴(ISR)을 실행하여 장치의 요청을 처리한다.
  4. 요청 처리 후, CPU는 이전 작업 상태로 복원하고 계속 실행한다.
- 장점:
  - CPU 자원을 효율적으로 사용할 수 있다.
  - 응답 시간이 짧고, 실시간 처리에 유리하다.
- 단점:
  - 처리 로직이 복잡하고, 우선순위 관리 및 충돌 처리가 필요하다.
  - 인터럽트가 자주 발생하면 오히려 성능 저하를 초래한다.

2. 폴링(Polling)
- 정의:
  - 폴링이란 CPU가 주기적으로 I/O 장치의 상태를 확인하여 데이터가 준비되었는지 또는 장치가 사용할 수 있는지 체크하는 방식이다.
- 특징:
  - 동기식 통신으로 CPU가 주기적으로 장치의 상태를 확인하여, 데이터가 준비되었는지 체크한다.
  - 시스템이 간단하여, 적은 수의 장치에서 사용하기 적합하다.
- 처리 과정:
  1. CPU가 주기적으로 I/O장치의 busy bit의 상태를 확인한다.
  2. CPU는 write bit를 설정하고, data-out register에 데이터를 작성한다.
  2. CPU는 전송할 데이터가 존재하면, command-ready bit을 변경한다.
  3. I/O 장치가 준비되면, Controller는 busy bit을 1로 변경하고, 전송을 수행한다.
  4. 전송이 완료되면, Controller는 busy bit, error bit, command-ready bit을 0으로 초기화한다.
  5. 위 과정을 반복한다.
- 장점:
  - 구현이 간단하고, 시스템 설계가 용이하다.
- 단점:
  - 장치가 준비되지 않은 경우에도 계속 체크하므로, CPU의 부담이 크다.
#### DMA (Direct Memory Access) 
- 정의:
  - CPU가 직접 개입하지 않고도 I/O 장치가 메모리에 데이터를 전송할 수 있도록 하는 방식이다.
- 특징:
    - 시스템 버스에 연결된 DMA 컨트롤러라는 하드웨어를 통해 DMA 입출력이 가능하다.
    - CPU의 개입을 최소화 할 수 있다.
- 입출력 과정
    ![image](/image/dma.png)
    1. CPU 는 DMA 컨트롤러에 입출력장치의 주소, 수행할 연산 (읽기/쓰기), 읽거나 쓸 메모리의 주소 등과 같은 정보로 입출력 작업을 명령한다.
    2. DMA 컨트롤러는 CPU 대신 장치 컨트롤러와 상호작용하며 입출력 작업을 수행한다. 이때 DMA 컨트롤러는 필요한 경우 메모리에 직접 접근하여 정보를 읽거나 쓴다.
    3. 입출력 작업이 끝나면 DMA 컨트롤러는 CPU에 인터럽트 요청을 걸어, 작업이 끝났음을 알린다.
- 장점:
  - CPU의 부하를 줄여, 시스템의 전체적인 성능을 높인다.
- 단점:
  - DMA 컨트롤러가 필요하므로, 추가적인 하드웨어 비용이 필요하다.

## 운영체제의 보안 (Security in Operating Systems)
#### 사용자 인증 (User Authentication)
- 운영 체제에서는 대표적인 사용자 인증 방식으로 비밀번호를 사용한다.
1. 비밀번호(Password)
   - 정의:
     - 시스템, 애플리케이션 또는 서비스에 접근하기 위해 사용자가 입력하는 비밀 정보이다.
   - 특징:
     - 사용자의 신원을 확인하기 위한 목적과 디렉토리 및 파일에 접근을 제한하기 위한 목적으로 사용한다.
     - 리눅스에서는 사용자의 비밀번호가 /etc/shadow 파일에 해시 형태로 존재한다.
   - 동작 방식:
     - 각 사용자는 본인만 아는 문자열을 비밀번호로 설정한다.
     - 비밀번호는 SHA-256 등 해시 알고리즘으로 암호화를 거쳐 저장된다.
   - 장점:
     - 인증이 간단하고 직관적이다.
     - 비밀번호 인증 시스템의 구현과 유지 관리의 비용이 저렴하다.
   - 단점:
     - 무차별 대입 등 종종 쉽게 추측될 수 있다.
     - 사용자가 기억하지 못 할 경우, 재설정의 번거로움이 있다.

#### 접근 제어 (Access Control) - 접근 제어 리스트(ACL), 역할 기반 접근 제어(RBAC)
1. 접근 제어 리스트(ACL)
   - 정의:
     - 접근 제어 목록을 설정한 것으로, 파일과 디렉토리 별로 권한을 설정한 목록이다.
   - 특징:
     - 파일, 디렉토리 등 각 object 별로 설정한다.
     - 사용자보다, object의 수가 많은 경우에 사용한다.
   - 동작 방식:
  ![image](/image/acl.png)Unix에서의 ACL
     - 각 파일 또는 디렉토리 별로 파일 소유자, 소유자 그룹, 다른 사용자에 대해 read, write, execute 권한을 설정한다.
   - 장점:
     - 구현이 간단하다.
   - 단점:
     - 사용자 간 권한을 일임하는 환경에서는 부적합하다.
     - 사용자가 많고, 지속적으로 변화하는 환경에서는 부적합하다.

2. 역할 기반 접근 제어(RBAC)
   - 정의:
     - 접사용자의 역할에 따라 시스템 자원에 대한 접근 권한을 관리하는 보안 모델이다.
   - 특징:
     - 파일, 디렉토리 등 각 object 별로 설정한다.
     - 사용자보다, object의 수가 많은 경우에 사용한다.
   - 동작 방식:
    
    ![image](/image/rbac.png)

    Solaris 10에서의 RBAC
     - 시스템 관리자는 다양한 역할을 정의하고, 각 역할에 필요한 권한을 할당한다.
     - 사용자는 하나 이상의 역할에 할당되고, 해당 역할에 따라 부여된 권한을 통해 자원에 접근한다.
   - 장점:
     - 개별 사용자의 액세스 또는 오브젝트 권한을 구성해야 하는 것에 효율적이다.
     - 역할에 따른 권한을 쉽고 빠르게 알 수 있다.
     - 권한 관리에 대한 부담이 줄어든다.
   - 단점:
     - 역할이 중복되면, 필요 이상의 많은 권한을 부여받아 보안에 취약할 수 있다.
     - 현실과 정책의 불일치로, 역할을 별도로 계속 만들면서 중복되는 권한이 생긴다.
#### 암호화 및 데이터 보호 (Encryption and Data Protection)
- 특징:
  - 리눅스에서 네트워크 통신을 암호화하기 위해서는 OpenSSH를 사용한다.
1. OpenSSH
   - 정의:
     - 네트워크 통신에 사용되는 TLS, SSL 프로토콜을 구현하는 데 사용하는 툴킷이다.
   - 특징:
     - 대부분의 OS에서 이용할 수 있다.
     - 대칭 및 비대칭 키 암호화를 지원한다.
   - 장점:
     - 다양한 암호화 알고리즘과 프로토콜을 지원하여 기밀성과 무결성을 보장한다.
     - 다양한 OS 및 언어에서 지원한다.
   - 단점:
     - 초기 설정이 다소 복잡할 수 있다.
     - 리소스 소모가 크다.
#### 보안 정책과 공격 방지 기법 (Security Policies and Attack Mitigation) - 방화벽, IDS/IPS, 악성코드 탐지
1. 방화벽
   - 정의:
     -  네트워크 트래픽을 감시하고, 미리 정의된 보안 규칙에 따라 허용하거나 차단하는 보안 장치이다.
   - 특징:
     - IP 주소, 포트, 프로토콜 등을 기반으로 트래픽을 필터링한다.
     - 접근 통제, 인증, 감사 및 로깅 등의 기능을 한다.
     - 구현 방식에는 패킷 필터링 방식(Packet Filtering), 상태 추적 방식(Stateful Inspection), 어플리케이션 게이트웨이 방식(Application Gateway) 등이 있다.
   - 동작 방식:
    패킷 필터링 방식(Packet Filtering)
     - 데이터 링크 계층(OSI Layer 2)에서 네트워크 계층으로 전달되는 패킷을 가로채서 해당 패킷 안의 주소(IP)와 서비스 포트를 검색하여 정의된 보안 규칙에 따라 서비스의 접근 허용 여부를 결정한다.
   - 장점:
     - 외부 공격으로부터 네트워크를 보호한다.
   - 단점:
     - 프로그램 내부에 포함된 악성 소프트웨어는 탐지가 어려움.
     - 악의적인 내부 사용자의 공격을 방어하는 데 한계가 있음.
2. IDS/IPS(Intrusion Detection System/Intrusion Prevention System)
   - 정의:
     -  IDS는 네트워크나 시스템에서 발생하는 비정상적인 활동을 감지하고 관리자에게 경고하는 시스템이고, IPS는 이를 확장하여 비정상적인 트래픽을 실시간으로 차단하는 시스템이다.
   - 특징:
     - IDS는 침입 여부를 감지하고 알리는 것, IPS는 침입 이전에 방지하는 것을 목적으로 한다.
     - IDS는 네트워크의 외부, IPS는 네트워크의 내부에 위치한다.
   - 장점:
     - 실시간으로 공격을 탐지, 차단한다.
   - 단점:
     - 잘못된 탐지가 발생할 수 있다.
3. 악성코드 탐지
   - 특징:
     - 리눅스에서 사용 가능한 악성코드 탐지 도구는 Aircrack-ng, ClamAV 등이 있다.
## 분산 및 병렬 처리 (Distributed and Parallel Processing)

#### 분산 시스템의 개념과 특성 (Concepts and Characteristics of Distributed Systems)

#### 클러스터링 및 로드 밸런싱 (Clustering and Load Balancing)

#### 병렬 처리와 병렬 컴퓨팅 (Parallel Processing and Computing)

#### 동기화와 일관성 유지 (Synchronization and Consistency)