📖 **Contents**
* [프로세스와 스레드의 차이](#프로세스와-스레드의-차이)



---

## 프로세스와 스레드의 차이
### 프로그램(Program)이란?
  * 사전적 의미 : 어떤 작업을 위해 실행할 수 있는 파일
### 프로세스(Process)란?
  * 사전적 의미 : 컴퓨터에서 연속적으로 실행되고 있는 컴퓨터 프로그램
    * 메모리에 올라와 **실행되고 있는 프로그램의 인스턴스(독립적인 개체)**
    * 운영체제로부터 시스템 자원을 할당받는 작업의 단위
    * 즉, 동적인 개념으로는 실행된 프로그램을 의미한다.
  * 할당받는 시스템 자원의 예
    * CPU 시간
    * 운영되기 위해 필요한 주소 공간
    * Code, Data, Stack, Heap의 구조로 되어 있는 독립된 메모리 영역
  * 특징 
    * ![process](../images/process.png)
    * 프로세스는 각각 도립된 메모리 영역(Code, Data, Stack, Heap의 구조)을 할당받는다.
    * 기본적으로 프로세스당 최소 1개의 스레드(메인 스레드)를 가지고 있다.
    * 각 프로세스는 별도의 공간에서 실행되며, 한 프로세스는 다른 프로세스의 변수나 자료구조에 접근할 수 없다.

**요약 : 프로그램을 실행시키면 프로세스다.**

### 스레드(Thread)란?
  * 사전적 의미 : 프로세스 내에서 실행되는 여러 흐름 단위
    * **프로세스의 특정한 수행 경로**
    * 프로세스가 할당받은 자원을 이용하는 실행의 단위
  * 특징 
    * ![thread](../images/thread.png)
    * 스레드는 프로세스 내에서 각각 stack만 따로 할당받고 Code, Data, Heap 영역은 공유한다.
    * 스레드는 한 프로세스 내에서 동작되는 여러 실행의 흐름으로, 프로세스 내의 주소 공간이나 자원들(힙공간 등)을 같은 프로세스 내에 스레드끼리 공유하면서 실행된다.
    * 같은 프로세스 안에 있는 여러 스레드들은 같은 힙 공간을 공유한다. 반면에 프로세스는 다른 프로세스의 메모리에 직접 접근할 수 없다.
    * 각각의 스레드는 별도의 레지스터와 스택을 갖고 있지만, 힙 메모리는 서로 읽고 쓸 수 있다.
    * 한 스레드가 프로세스 자원을 변경하면, 다른 이웃 스레드(sibling thread)도 그 변경 결과를 즉시 볼 수 있다.