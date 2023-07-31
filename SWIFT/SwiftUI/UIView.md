# UIView

스크린 위의 직사각형의 공간을 관리하는 객체 

즉, UI를 구성하는데에 사용되는 객체로써 화면에 보이는 모든 요소들의 기본 클래스이다.
앱이 사용자와 직접 상호작용하는 주 방법으로 여러가지 구성요소들이 존재한다.

* Draw, Animaiton<br>
직사각형 영역 안에 컨텐츠를 그릴 수 있고, `view`의 속성들을 통해서 애니메이션을 만들 수 있다.

* Layout, subview management<br>
view들은 0개 이상의 `subview`를 가질 수 있으며, `size`나 `position`을 조정할 수 있다.
Auto Layout을 통해서 View의 상속 계층에 따라서 반응하도록 만들 수 있다.

* Event handling<br>
`UIResponder`의 서브클래스로써 터치와 다른 타입의 이벤트 등에 반응할 수 있고, 일반적인 제스쳐를 처리할 수 있도록 `gesture recognizers`를 사용할 수 있다.

```
// UIView 생성
let view = UIView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))```