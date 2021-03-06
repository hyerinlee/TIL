# 렌더링
모델링된 3D 객체를 실감나게 보이도록 처리하는 과정.  
### 렌더링 과정
와이어프레임 모델 -> 은면제거 -> 쉐이딩 -> 투명한 물체의 표현 -> 텍스쳐 매핑 -> 그림자 생성
- **은면제거**: 보이지 않는 면을 렌더링하지 않음으로써 계산량을 줄인다.
- **쉐이딩**: 객체로부터 관찰자의 눈에 들어오는 빛의 반사량과 성분을 계산한다. Gouraud, Phong 등 다양한 쉐이딩 기법이 있다.
- **투명한 물체의 표현**: 물체의 투명도에 따른 빛의 투과량을 계산한다.
- **텍스쳐 매핑**: 이미지를 3D객체에 입힘으로써 저비용으로 고품질의 디테일을 표현한다.
- **그림자 생성**: 태양,전구 등의 광원에 의해 생기는 그림자를 표현한다.

이 단계들을 거쳐 최종적으로 각각의 픽셀 색이 결정되면 렌더링이 완료된 것이다.

<br/>

# 조명 모델
객체가 받은 빛이 어떻게 반사되어 눈에 들어오는가?를 기술한 모델.
### 전역/지역 조명모델
현실 세계에서 빛이 눈에 들어오는 경로는, 
단지 광원으로부터 객체로 직접 입사된 빛(Direct light)뿐만 아니라 주위의 여러가지 다른 객체에서 반사되고 또 반사되어 들어온 빛(Indirect light)들까지 
포함하여 매우 복잡하게 이루어져 있다.  
- **지역 조명모델**: (Direct light) 광원으로부터 직접 입사된 빛만을 고려한 모델이다. 여기서는 주위 객체를 고려하지 않고 대신 주변광(Ambient 
light)이라는 개념을 사용하여, 전체 공간에 일정한 빛을 줌으로써 빛이 닿지 않는 어두운 부분까지 빛을 밝혀준다.
따라서 속도는 빠르지만 다소 비현실적이다.
- **전역 조명모델**: (Direct light + Indirect light) 주위 객체에서 반사되어 들어온 빛까지 고려한 모델이다. 
어느정도 현실적이지만 연산량이 많아 속도가 느리다.
<br/>

# 빛
**넓은 의미의 빛**은 모든 종류의 전자기파(전기장과 자기장이 얽혀 직진하는 파동)를 지칭한다.  
**좁은 의미의 (우리가 흔히 말하는) 빛**은 사람의 눈으로 볼 수 있는 영역인 **가시광선**을 말한다.  
빛의 속도는 항상 일정하며, *빛의 속도(c) = 파장(λ) × 주파수(f)* 이므로 파장과 주파수는 반비례 관계이다.  
(파장:한번의 진동 거리 / 주파수:1초 당 진동 횟수)  
그래픽스에서 다루는 빛 역시 가시광선 영역의 전자기파이다.  
그리고 이러한 빛이 광원으로부터 출발하여, 물체에 의한 반사/흡수/굴절을 거쳐 눈으로 들어와 자극함으로써 **색**을 인지하게 된다.

### 광원의 종류
- 주변 광원(Ambient light): 배경조명. 방향과 위치 없이 색깔과 강도의 차이만 존재하며, 공간 전체에 균일하게 비춘다. 실제로 존재하지 않는 형태의
광원이지만, 주변 물체에 의해 반사된 빛을 근사적으로 표현하기 위해 사용한다.
- 점광원(Point light): 빛이 점으로부터 사방으로 뻗어나가는 형태의 광원. 광원의 방향과 위치에 따라 강도가 달라진다. ex)전구
- 방향성 광원(Directional light): 위치 없이 방향만 존재하여 일정한 방향으로 무한히 퍼져나가는 광원. 실제로 존재하지 않는 형태의 광원이지만, 태양처럼 극히 먼 거리의 빛을 근사적으로 표현하기 위해 사용한다.
- 스포트라이트(Spot light): 특정 위치와 범위에만 비추는 특수 조명. ex)공연장의 조명

### 빛의 반사
- 난반사(Diffuse reflection)
- 정반사(Specular reflection)

## 색의 3속성
색은 파장/주파수에 의해 결정된다. 예를 들면 파장이 길수록 빨간색에 가깝고 파장이 짧을수록 보라색에 가깝다.  
색의 3가지 속성을 다음과 같이 분류할 수 있다.
- 색상: 우세 주파수(반사된 빛 중 가장 많은 에너지를 지닌 파장의 주파수)에 따라 색상이 결정된다.
- 명도: 색상과 관계없이 빛에너지의 총량에 따라 명도가 결정된다.
- 채도: 색상의 순도를 뜻한다. 색상 에너지와 백색 에너지의 차이로 채도가 결정된다.
