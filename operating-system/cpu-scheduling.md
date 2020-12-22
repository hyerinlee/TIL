# 스케줄링
### 💡 단일 / 다중 프로그래밍 시스템
**단일 프로그래밍 시스템**에서 단일프로세서는 한번에 하나의 프로세스만 실행(run)이 가능하다.  
실행중인 프로세스가 입출력을 요청하면 입출력이 완료될 때까지는 CPU를 사용하지 않는데, 한번에 하나의 프로세스만 실행된다면
이 입출력에 의해 발생하는 대기시간 동안 CPU는 놀게 된다.  
**다중 프로그래밍 시스템**에서는 이렇게 실행중인 프로세스 A가 입출력에 의해 CPU를 사용하지 않는 시간 동안 다른 프로세스 B가 CPU를 사용할 수 있도록 한다.  
즉 단일프로세서 상에서 여러 프로세스를 실행할 수 있기 때문에 CPU 이용률이 높아진다.  
<br/>

다중 프로그래밍 시스템에서, 어떤 프로세스에게 CPU를 할당할 것인지를 결정하는 작업을 **스케줄링** 이라고 한다.  

### 스케줄링의 목적
여러 프로세스들이 최대한 **효율적으로 실행**되기 위해 스케줄러는 여러가지 기준에 따라 프로세스들을 스케줄링해야 한다.  
'효율적으로 실행된다'는 것은 다음과 같은 의미이다. 
- 공정성: 모든 프로세스에게 공정하게 할당된다.
- 처리율 증가: 단위시간 동안 프로세스 처리율이 높아진다.
- 우선순위: 우선순위가 높은 프로세스가 먼저 실행된다.
- 오버헤드 최소화
- 대기시간 최소화  
...  
위와 같은 항목들을 기준으로 여러 스케줄링 알고리즘의 효율성을 평가,비교한다.

### 스케줄링 단계
스케줄링 단계는 크게 3단계로 분류된다.  
- **장기 스케줄링**: 메모리-디스크 사이 스케줄링. 어떤 프로그램을 디스크로부터 메모리로 가져와 적재할지를 결정한다.  
작업 스케줄링 또는 승인 스케줄링이라고도 한다. 호출 빈도수가 적다.
- **중기 스케줄링**: 너무 많은 프로세스가 적재되어 프로세스 간 CPU 할당 경쟁이 심해질 때,  
일부 프로세스를 메모리에서 디스크로 보내고(swap-out) 나중에 메모리에 여유가 생기면 다시 메모리로 적재(swap-in)한다.
- **단기 스케줄링**: CPU-메모리 사이 스케줄링. 메모리에 현재 적재된 작업 중 실행할 프로세스를 선택해 CPU를 할당한다.  
보통 CPU 스케줄링은 이 단계를 말한다. 호출 빈도수가 가장 많다.