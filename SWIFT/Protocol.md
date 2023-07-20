# 프로토콜 (Protocol)
자바에서 `interface`와 같은 역할을 하는 것<br>
특정 역할을 위해서 메소드, 프로퍼티, 등의 요소를 담고 있는 것이다.<br>
이는 클래스와 구조체, 열거형과 비슷하다.
```
protocol SomeProtocol {
    // protocol definition goes here
}
```

## 프로토콜을 사용하는 이유
1. 다중 상속
> 클래스에서는 다중 상속을 지원하지 않기 때문에 여러가지 프로토콜을 채택하여 사용하기 위해서 프로토콜을 사용한다.
2. 코드 재사용 및 확장성
> 코드를 재사용하고 기존 코드를 확장할 수 있다.
3. 유연성
> 타입이 특정 프로토콜을 채택한다면, 해당 프로토콜을 사용하는 함수, 메서드 또는 제네릭 타입에 해당 타입을 사용할 수 있다.

## 프로토콜의 타입 지정
따르는 프로토콜의 이름을 콜론 뒤에 적는다.<br>
클래스의 경우에는 그것이 서브 클래스일 경우에는 수퍼 클래스를 먼저 적고 뒤에 프로토콜 네임을 적는다.
```
struct SomeStructure: FirstProtocol, AnotherProtocol {
    // structure definition goes here
}
```
```
class SomeClass: SomeSuperclass, FirstProtocol, AnotherProtocol {
    // class definition goes here
}
```

## 프로토콜 요구사항
프로퍼티의 이름과 타입, `getable`, `setable`을 지정해주어야한다.<br>
/* 필수 프로퍼티는 무조건 `var`로 선언해주어야한다!!
```
protocol SomeProtocol {
    var mustBeSettable: Int { get set }
    var doesNotNeedToBeSettable: Int { get }
}
```