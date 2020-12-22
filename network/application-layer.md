# 애플리케이션 계층
네트워크 계층 중 가장 상위에 해당하는 계층.  
각 호스트에서 실행되는 네트워크 애플리케이션 프로세스가 어떻게 통신하는지에 대한 방법을 정의한다.  
<br/>

## 📌네트워크 애플리케이션 구조
호스트 간 통신이 이루어지는 각종 네트워크 애플리케이션(웹,전자메일 등)에서, 각 호스트가 어떤 역할을 갖는가에 따라 다양한 구조를 갖는다.  
현대 네트워크 애플리케이션에 사용되는 두 가지 우수한 구조로 **클라이언트-서버** 구조와 **P2P(Peer-to-Peer)** 구조가 있다.  

### 클라이언트-서버 구조
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fb/Server-based-network.svg/200px-Server-based-network.svg.png" width="150">

이 구조는 **항상 켜져 있는 호스트와, 그에게 요청하는 많은 호스트들**로 이루어져 있다.  
항상 켜져있는 호스트를 `서버`, 그에게 요청하는 많은 호스트를 `클라이언트` 라고 한다. `클라이언트`는 가끔 혹은 항상 켜져있을 수 있다.  
`클라이언트`끼리는 서로 직접 통신하지 않는다.(예: 웹 애플리케이션에서, 2개의 브라우저가 서로 직접 통신하지 않는다.)  
(대형 서비스가 이런 구조를 이루고 있을 경우에는 무수한 클라이언트의 요청을 하나의 서버가 감당하기 어려우므로, 많은 서버를 갖춘 '데이터 센터'를 보유하고 있다.)

### P2P 구조
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/P2P-network.svg/200px-P2P-network.svg.png" width="150">

이 구조는 항상 켜져있는 서버에 아예 의존하지 않거나 최소한만 의존하고, **통신은 호스트들끼리 직접 하도록 한다**.  
여기서는 호스트들을 `피어`라고 부른다. `피어`는 간헐적으로 연결된다.  
피어는 서버도 될 수 있고 클라이언트도 될 수 있다.  
(예: P2P 파일 공유 시스템에서, 파일을 내려받는 피어는 '클라이언트'이고 올리는 피어는 '서버'이다.)  
<br/>

## 📌프로세스 간 통신

### 클라이언트와 서버 프로세스
네트워크 애플리케이션에서, 서로 다른 호스트들에서 실행되는 프로세스끼리는 네트워크를 통해 **메시지**를 교환하여 통신한다.  
이때 통신하는 한쌍의 프로세스는 통신을 위해 접속을 초기화하는 프로세스와 접속을 기다리는 프로세스로 이루어져 있다.  
접속을 초기화하는 프로세스를 **클라이언트 프로세스**, 접속을 기다리는 프로세스를 **서버 프로세스**라고 한다.  
(예1: 웹 애플리케이션에서, 브라우저 프로세스는 클라이언트이고 웹서버 프로세스는 서버이다.)  
(예2: P2P 파일 공유 시스템에서, 파일을 요청하는 피어 A는 클라이언트이고 요청받는 피어 B는 서버이다.)