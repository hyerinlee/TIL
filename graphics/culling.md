# 컬링(Culling)
보이지 않는 오브젝트를 연산에서 제외시키는 작업. 불필요한 물체들을 렌더링에서 배제함으로써 렌더링 부하를 줄여준다.  
Backface Culling, View Frustum Culling, Occlusion Culling, Portal Culling 등이 있다.  
<img src="https://user-images.githubusercontent.com/46877318/103092315-2eabf180-463a-11eb-96e3-a9a0c558b4eb.jpg" width="350">  

*※컬링과 클리핑(Clipping)의 차이: 컬링은 아예 연산을 하지 않는 것이고, 클리핑은 연산 후에 보이지 않는 부분을 잘라내는 것이다.*  
<br/>

## 📌 Backface Culling
불투명한 객체의 뒷면을 제거(렌더링하지 않는다). **단, 반투명 상자와 같이 뒷면이 보여야 하는 경우는 제외*  
<br/>

## 📌 Frustum Culling
절두체 형태의 카메라 시야 내에 들어오지 않는 오브젝트를 제거.  
<br/>

## 📌 Occlusion culling
다른 오브젝트에 의해 가려지는 면(은면)을 제거.  
### 은면제거 알고리즘 기법
1. **객체공간법**: 공간상 객체의 위치관계를 계산해 은면이 되는 부분을 판단하는 방법.  
은선제거 알고리즘, 깊이정렬 알고리즘이 있다.
2. **이미지공간법**: 투영된 픽셀에서 객체가 보이는지의 여부를 검사하는 방법.  
Z-버퍼 알고리즘, 레이캐스팅 기법이 있다.  
주로 이미지공간법을 사용한다.

### 은면제거 알고리즘 처리 개념
은면을 제거하기 위해 객체의 각 표면을 거리에 따라 정렬(Sorting)한다. 투영면에 가장 가까운 면을 선택해 그린다.

### 다면체 뒷면의 제거
은면제거의 첫단계에서 이용되는 것으로, 빠르고 간단하게 뒷면을 찾는 객체공간 방법이다.  
일반적으로 다면체의 약 50% 면이 제거된다.  
다면체의 뒷면인지를 판단하기 위해 법선벡터와 시선방향 벡터를 내적하여, 그 결과값이 양수인지 음수인지에 따라 은면이 결정된다.
<br/>
