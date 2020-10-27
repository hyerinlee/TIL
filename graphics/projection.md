# 투영
3차원 객체를 2차원 출력장치에 맵핑하는 작업.
## 투영의 종류
<img src="https://user-images.githubusercontent.com/46877318/97344102-aaecb780-18cb-11eb-9261-7755b3f20fa2.jpg" width="800"/>  

> *종종 Orthographic/Axonometric을 별개의 프로젝션으로 분류하기도 하나(Orthographic = Multiview),  
투영선이 투영면에 직교한다는 공통점과, 게임엔진·모델링 프로그램에서 주로 표현되는 Orthographic view가
Axonometric이 포함된 view인 것을 고려하여 Axonometric이 Orthographic에 속하는 분류방법으로 작성하였다.
(Orthographic = Multiview + Axonometric))*
<br/>

## 평행투영
### 직교투영
투영선이 투영면에 직교한다.
- 다중관측투영(Multiview Projection): 투영면이 x,y,z축 중 하나와 직교함에 따라 해당 좌표값이 모두 0이 된다. 시점 위치가 위,정면,측면 등으로 제한되어 있다.
- 축측투영(Axonometric Projection): x,y,z축이 이루는 각도에 따라 등축/이축/삼축투영으로 나뉜다.
### 경사투영
<br/>

## 원근(투시)투영
소실점의 갯수에 따라 1점/2점/3점투시로 나뉜다.
