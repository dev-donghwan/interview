# Thread

- Process에서 실행되는 흐름의 단위라고 할 수 있습니다.
- 하나의 Process는 1개 이상의 Thread를 가지고 있습니다.
- Thread는 Process에 할당된 Virtual Memory 내부에 자신의 데이터 영역을 가집니다.
- 개별적으로 Thread Local Storage와 Stack, PC Register 공간을 가집니다.
- 나머지 Heap, Code, Data(Static) 영역은 Thread들이 모두 공유합니다.
- 공유 자원이 존재하기 때문에 동시성과 동기화가 매우 중요합니다.
- Light-Weight-Process라고 불리고 그에 맞게 적은 자원으로 빠른 성능을 낼 수 있습니다.
- 각 Thread는 우선순위를 할당하여 우선적으로 CPU를 할당 받을 수 있습니다.
