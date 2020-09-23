# Strategy Pattern<br>
인터페이스(접근점)를 통해 동일 계열 알고리즘군(전략)을 교환하여 사용할 수 있도록 한다.

예) 게임에서 적을 공격할 수 있는 여러 무기(창,검,도끼 등...)를 구현하고자 한다.  
무기들은 공격방법은 다르지만 어쨌든 '공격'이라는 공통된 기능을 갖는다.  
그러므로 무기(Weapon)로 공격한다(attack)는 틀을 갖추어 놓고(=인터페이스), 상황에 맞는 무기(=전략)만 설정하면 되도록 설계하는 것이 편할 것이다.

*Weapon.java*
```java
package com.StrategyPattern;

public interface Weapon(){
  public void attack();
}
```
*Sword.java* (*Sword, Spear, Axe, ...)
```java
package com.StrategyPattern;

public class Sword implements Weapon{
  @Override
  public void attack(){
    System.out.println("검 공격");
  }
}
```
*Main.java*
```java
package com.StrategyPattern;

public class Main {
  public static void main(String[] args){
    Weapon weapon = new Sword();
    weapon.attack();
  }
}
```
