# 들어가기 전에
### 트리란?
[![Tree](http://www.tutorialspoint.com/data_structures_algorithms/images/binary_tree.jpg)](https://sites.google.com/site/learnwithdatastructures/content/graphs)  
트리란 이름대로 마치 위아래가 거꾸로 된 나무의 모양과 같이 계층적 구조를 갖는 자료구조로, `노드(Node)`와 두 노드를 잇는 선 `링크(Link)`(edge 또는 branch라고도 함) 로 구성되어 있다.  
가장 최상위 노드는 루트(Root)노드, 최하위 노드는 리프(Leaf)노드라고 하며 어떤 노드와 그 노드의 하위 노드는 각각 부모-자식 관계를 갖는다.


### 트리의 기본 성질
- 트리의 노드가 N개라면, 링크는 항상 N-1개이다.
- 어떤 노드 A로부터 다른 어떤 노드 B로 가는 경로는 오직 하나뿐이다.(같은 노드를 재방문하지 않는다고 가정했을 때)


### 이진 트리
이진 트리는 모든 노드의 자식 노드가 최대 2개인 트리를 말한다.  
각 노드의 자식 노드는 왼쪽 노드/오른쪽 노드로 구분짓는다. 따라서 값이 같더라도 위치가 다르면 이는 서로 다른 트리인 것이다.  
<img src="https://user-images.githubusercontent.com/46877318/94483819-6ca1a100-0216-11eb-9fb5-6c341573d707.jpg" width="40%">  


# 이진 탐색 트리
