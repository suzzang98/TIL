# 좋은 코드를 짜는 법
### 그동안의 나..
그동안의 나는 한 파일을 만들고 그 안에서 100줄이 되든 200줄이 되든 나열하는 형태로 코드를 짰다. <br>
이것의 단점은 너무 긴 코드에서 오류가 났을 때 어떤 부분에서 오류가 발생했는지 쉽게 알 수 없다는 것이다. 또한 분업이 필수인 개발의 세계에서는 파일 한개로 모든 것을 해결하면 다른 사람이 수정하기도 쉽지 않고 관리도 힘들다.<br>
그렇기 때문에 코드를 다른 여러개의 파일을 통해서 관리하는 것이 훨씬 이득이다.
<br>

## 코드를 분리하는 것의 기준?
대부분의 코드에는 `function`과 `class`가 있을 것이다. 하지만 어떤 코드는 `function`만으로도 작동을 하게 만들 수 있다. 여기에서 든 의문점은, 그럼 도대체 어떤 기준을 통해서 파일을 구분지어야하지? 였다.<br>
어떤 기능을 하나 만들 때, 충분히 그 기능 하나만으로도 클래스를 사용하도록 만들 수도 있고, 그렇게 되면 너무 비효율 적일것같다는 생각을 했다.<br>
그래서 튜터님께 가서 여쭤보았다. 얼마나 작은 단위로 쪼개야하는지.

보통은 그것의 기능별로 파일을 구분짓는 것이 맞다. 하지만 내가 생각한 짜잘한 단위의 기능보다는 비슷한 역할을 하는 기능들을 최대한 묶어서 하나의 `class`로 엮어주고, 그것을 분리시키는 것이 깔끔하다고 말씀해주셨다.

이것을 모듈화라고 하고, 그것에 대해서 좀 더 공부해보았다.

## 모듈화?
모듈화란 파일단위나 모듈 단위로 하나의 코드를 쪼개놓는 것을 말한다.
모듈이나 파일로 코드를 분리함으로써 각각의 코드 조각은 독립적으로 존재할 수 있게 해준다.

### 모듈화의 장점
1. 모듈화와 코드의 재사용성
>> 관련된 코드들을 하나의 모듈로 묶어서 재사용 가능한 블록으로 만들 수 있다. 또한 다른 프로젝트에서도 해당 모듈을 가져와서 사용함으로써 코드의 재사용성이 증가한다.

2. 인터페이스 제한과 정보 은닉
>> 모듈의 외부에서는 공개된 인터페이스만 접근할 수 있도록 설계할 수 있다. 내부 구현 상세를 숨기고 캡슐화할 수 있어서 모듈 간의 결합도가 낮아지고, 각 모듈은 독립적으로 개발 및 유지보수가 가능해진다.

3. 코드 가독성과 유지 보수성
>> 코드를 적절하게 모듈로 분리하면 코드의 가독성이 향상되고, 코드 간의 관계를 이해하기 쉬워진다. 또한 수정이 필요한 경우 해당 모듈만 수정하면 되므로 유지 보수성이 좋아진다.

4. 애플리케이션 아키텍처 개선
>> 코드를 모듈화하여 애플리케이션을 컴포넌트 단위로 구성할 수 있다. 이렇게 하면 애플리케이션의 아키텍처가 개선되고, 큰 규모의 프로젝트에서도 구조를 더욱 명확하게 관리할 수 있다.

## 캡슐화?
객체 지향 언어의 특징으로, 서로 연관있는 속성과 기능을 하나의 캡슐로써 만들어 데이터를 외부로부터 보호하는 것을 말한다. 

즉 외부로부터 클래스에 정의된 속성과 기능을 보호하고 필요한 부분만 노출되어서 각 객체의 독립성을 지키는 목적을 가진다. 

`접근제어자`를 통해서 이것을 관리하는데, swift에서는 `public`과 `static`, `private`를 통해서 코드의 공개 범위를 조절할 수 있다. 