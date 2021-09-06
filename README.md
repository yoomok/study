# study

state transition diagram

사각형(상태)과 화살표(상태 전이)로 상태와 상태전이를 표현
프로세스의 상태를 나타내는것?

개체가 가질 수 있는 모든 상태, 개체가 상태를 변경하는 이벤트, 전환이 발생하기 전에 충족되어야 하는 조건 및 수행된 활동을 설명한다.
전체에서 개별 개체의 동작을 설명하는 데 유용하다.


UML 표기법

![XDD6232imagelistfilename1](https://user-images.githubusercontent.com/89113823/132148379-8aab49f5-3ea2-43b4-a357-81b6bf2c0cbd.jpg)


state(상태) - 어떤 조건을 만족시키거나, 동작을 수행하거나, 사건을 기다리는 객체의 수명 동안의 조건, 둥근모서리의 사각형으로 표시   
Event(이벤트) - 상태 전환을 트리거할 수 있는 발생, transition을 유발하는 이벤트는 transition 위에 이벤트 이름이 표시  
ex) 시스템 외부의 명시적 신호, 시스템 내부의 호출, 지정된 기간의 경과 또는 지정된 조건이 True가 되는것  
Guard(가드) - True인 경우 이벤트가 전환을 일으킬 수 있도록 하는 부울 표현식  
Transition(전환) - 객체 내의 상태 변화, 실선으로 표시  
Action(조치) - 상태 변경에 대한 응답으로 개체가 수행하는 하나 이상의 작업  
  
  
뮤텍스(Mutex)  
mutual exclusion = 상호 배제  
Critical Section을 가진 Thread들의 running time이 서로 겹치지 않게, 각각 단독으로 실행되게 하는 기술이다.
*Critical Section : 프로그램 상에서 동시에 실행될 경우 문제를 일으킬 수 있는 부분.  

만약 어느 Thread에서 Critical Section을 실행하고 있으면 다른 Thread들은 그 Critical Section에 접근할 수 없고 앞의 Thread 가 Critical Section을 벗어나기를 기다려야 한다.  
  
자원에 대한 접근을 동기화 하기 위해 사용되는 상호배제 기술이다.  
프로그램이 시작될 때 고유한 이름으로 생성된다.  
뮤텍스는 Locking 메커니즘으로 오직 하나의 쓰레드만이 동일한 시점에 뮤텍스를 얻어 임계영역에 들어올 수 있다. 그리고 오직 이 쓰레드만이 임계영역에서 나갈때 뮤텍스를 해제할 수 있다.  

wait(mutex);  
...  
Critical Section  
...  
signal(mutex);  
  
  
  
세마포어(semaphore)
  
데드락을 피하기 위한 기술 중에 하나이다.  
Thread가 Critical Section에 접근할때 해당 Thread는 세마포어의 카운트를 감소시키고 수행이 종료된 후엔 세마포어의 카운트를 원래대로 증가시킨다.   
즉 일종의 신호등의 역할을 한다. (카운트와 flag의 역할?)  
  
  
세마포어는 Signaling 메커니즘이라는 점에서 뮤텍스와 다르다. 세마포어는 락을 걸지 않은 쓰레드도 Signal을 보내 락을 해제할 수 있다는 점에서, wait 함수를 호출한 쓰레드만이 signal 함수를 호출할 수 있는 뮤텍스와 다르다.  
  
세마포어는 동기화를 위해 wait와 signal이라는 2개의 atomic operations를 사용한다.  
  
wait를 호출하면 세마포어의 카운트를 1줄이고, 세마포어의 카운트가 0보다 작거나 같아질 경우에 락이 실행된다.   
  
  
  
  
  
*Thread : 어떠한 프로그램, 프로세스 내에서 실행되는 흐름의 단위
