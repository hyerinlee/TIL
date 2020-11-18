# Design Patterns

디자인 패턴을 적용함으로써 코드의 `확장성`, `재사용성`, `유지보수성`을 높인다.  

![design-pattern-relationship-diagram](https://user-images.githubusercontent.com/46877318/98826716-6a6b6d00-2479-11eb-8a51-948c95db9523.png)

GoF에서는 23가지의 디자인 패턴을 다음 3가지 유형으로 분류한다.
## 📌Creational Pattern
객체 생성과 관련된 패턴들
- [Factory Method](https://github.com/hyerinlee/TIL/blob/master/design-patterns/factory-method.md) - 객체 생성부분을 서브클래스가 담당하도록 위임한다.
- Abstract Factory
- [Builder](https://github.com/hyerinlee/TIL/blob/master/design-patterns/builder.md) - 객체의 생성과 표현을 분리하여 표현이 서로 다르더라도 **구축 공정이 같도록** 한다.
- [Prototype](https://github.com/hyerinlee/TIL/blob/master/design-patterns/prototype.md) - 생산비용이 높은 인스턴스를 프로토타입(원형)의 **복제**를 통해 쉽게 생성한다.
- [Singleton](https://github.com/hyerinlee/TIL/blob/master/design-patterns/prototype.md) - **단 하나**의 인스턴스를 만들고 전역적으로 접근하도록 한다.

## 📌Behavioral Pattern
상호작용을 패턴화한 것들
- Interpreter - 간단한 언어의 문법을 정의하고 해석할 수 있도록 한다.
- Template method
- Chain of Responsibility - **사슬처럼 연결**된 객체들이 요청을 처리하거나 처리하지 못하면 다음 객체에 넘기며 요청을 수행한다.
- Command
- Iterator
- Mediator
- Memento - 객체의 **상태 정보를 저장**하여 이전 상태로 복원 가능하도록 한다.
- Observer
- State
- [Strategy](https://github.com/hyerinlee/TIL/blob/master/design-patterns/strategy.md) - 인터페이스(접근점)를 통해 동일 계열 알고리즘군(전략)을 교환하여 사용할 수 있도록 한다.
- Visitor

## 📌Structural Pattern
프로그램 구조 관련 패턴들
- [Adapter](https://github.com/hyerinlee/TIL/blob/master/design-patterns/adapter.md) - 어댑터를 사용하여 **호환**되지 않는 인터페이스를 사용 가능하도록 변경한다.
- Bridge
- Composite - 객체 관계를 **트리** 구조로 구성하여 단일객체와 복합객체를 동일하게 취급할 수 있도록 한다.
- Decorator - 객체에 추가 기능이 필요할 때 유연하게 **확장** 가능하도록 한다.
- Facade - 복잡한 서브시스템을 감싼 **퍼사드(외관)** 객체를 제공함으로써	클라이언트가 서브시스템을 고수준 인터페이스를 통해 단순하게 사용할 수 있도록 한다.
- Flyweight - 일부 속성이 다른 다량의 객체가 필요할 때 일일이 인스턴스를 만들지 않고 하나의 객체를 **공유**함으로써 메모리를 절약하도록 한다.
- Proxy - 객체의 접근 제어를 위해 동일한 인터페이스를 갖는 **대변인** 객체를 제공한다.

