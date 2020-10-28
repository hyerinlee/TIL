# 빌더 패턴
*※ GoF 빌더패턴과 Effective Java 빌더패턴 설명에 관점상 차이가 있다.*  
<br/>

## GoF의 빌더 패턴
> *Separate the construction of a complex object from its representation  
so that the same construction process can create different representations.*

복잡한 객체의 '생성과 표현의 분리'를 통해 서로 다른 표현임에도 동일한 구축 공정을 제공하도록 한다.

<br/>

## Effective Java의 빌더 패턴
파라미터가 많은 인스턴스 생성 시 좀더 깔끔하고 유연하게 생성하도록 한다.  
빌더 패턴을 사용하면 (인자가 많음으로써 생기는) 다음과 같은 문제가 해결된다.  
(1)가독성이 좋지 않다.  
(2)인자 순서를 정확히 알고있어야 한다.  
(3)각 선택적 인자의 유무 경우마다 생성자를 만들어주어야 한다.  

### 자바빈 패턴을 사용했을 때와의 차이점
자바빈 패턴에서 setter 메서드를 사용하여서도 (1),(3)번을 해결할 순 있지만,  
한번에 생성하는 것이 아니라 생성한 객체에 setXXX()를 사용하는 구조이다. -> 객체 일관성이 깨진다.  
또한 setter 메서드가 있어 변경불가(immutable)한 클래스를 만들수 없다.  

빌더 패턴을 사용하면 이 문제가 해결된다.
