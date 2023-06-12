# Process

## Features

- Process라는 것은 OS가 관리하는 관리의 단위를 의미합니다.
- 코드로 이루어진 Program을 Memory에 적재하는 것을 Process라고도 합니다.
- Process가 생성될 때, Virtual Memory를 할당받고 이 것이 Process의 메모리입니다. 이 때, Virtual Memory는 실제 Physical적인 Memory 공간을 부여받는게 아닌 가상의 공간을 의미합니다. Virtual Memory는 RAM + HDD로 구성되어 있고 Logical합니다.
- Process는 할당받은 Virtual Memory에 Code, Data(Static), Stack, Heap 영역을 할당하여 사용합니다.
- Process는 최소 1개 이상의 Thread를 가집니다. 이때 Thread를 N개 사용하는 환경을 Multi-Threading 환경이라고 합니다.
- 프로그램의 처리 단위를 Thread에 중점을 두어 처리하면 Multi-Threading, Process에 중점을 두어 처리하면 Multi-Tasking이라고 합니다.
- OS는 이러한 Process를 관리하기 위해서 Process Control Block를 활용하여 관련 데이터를 저장합니다. 여기에는 다영한 정보가 저장됩니다. (Life Cycle과 관련이 있습니다.)
- CPU에 속한 Core의 갯수가 실제로 연산을 수행합니다. 실제 환경에서는 많은 수의 Process와 더 많은 수의 Thread가 있지만 Core를 활용한 시분할처리로 굉장히 빠르게 상태가 전이되기 때문에 사용자는 마치 동시에 모두가 처리되는거처럼 느껴집니다.

<br>

## Memory Area
### Code
Process가 실행 가능한 명령어를 포함하는 실제 코드 또는 명령어가 저장되는 공간입니다. <br><br>

### Data(Static)
초기화된 전역 변수와 정적 변수들을 포함하는 공간입니다. Process가 실행되는 동안 유지됩니다. <br><br>

### Stack
Process의 지역 변수와 함수 호출에 관한 정보를 포함합니다. <br><br>

### Heap
동적으로 할당된 메모리를 포함합니다. 실행 중에 동적으로 메모리를 할당하고 해제하는 데 사용합니다. <br><br>

<br>

## Life Cycle
### Creation(생성)
새로운 Process Instance를 만드는 과정을 의미합니다. PCB를 생성하고 초기화하는 과정을 실행합니다.<br><br>

### Ready(준비)
Process가 실행을 기다리는 상태를 의미합니다. 다른 의미로는 CPU를 차지하기 위한 경쟁상태에 있다고 할 수 있습니다. OS는 준비 상태에 있는 Process를 대기 Queue에 넣고 CPU를 얻을 수 있도록합니다.<br><br>

### Runnin(실행)
CPU를 할당받아 실제로 동작을 수행하는 상태입니다. Interrupt 발생 또는 CPU 할당 시간이 종료될 때까지 실행됩니다.<br><br>

### Waiting(대기)
다른 Process의 신호를 기다리는 상태를 의미합니다. 예를 들어 sleep 또는 suspend가 일어난 경우 대기 상태로 전환됩니다.<br><br>

### Termination(종료)
실행이 완료되었거나 강제로 중단된 상태를 의미합니다. PCB를 제거합니다.<br><br>
