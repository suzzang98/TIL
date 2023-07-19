# 클로저(Closure)
* 이름없는 함수, 코드블록 - 람다 함수와 비슷하다.
* 상수나 변수의 참조를 캡쳐해 저장할 수 있다.
* 비동기 처리가  필요할 때 사용할 수 있다.

## 클로저의 종류
* 전역 함수 : <strong>이름이 있고</strong> 어떤 값도 캡쳐하지 않는 클로저
* 중첩 함수 : <strong>이름이 있고</strong> 관련한 함수로 부터 값을 캡쳐할 수 있는 클로저
* 클로저 표현 : 경량화 된 문법으로 쓰여지고 관련한 문맥에서 값을 캡쳐할 수 있는 <strong>이름이 없는</strong> 클로저

-> 즉 익명함수도 이름이 있는 함수도 모두 클로저에 포함된다!<br>
```클로저 ⊃ 함수 ```

## 클로저의 표현식
```
{(Parameters) -> Return Type in
    // 실행 구문
}
```
익명함수이다 보니 func을 사용하지 않는다.
```
// 함수로 썼을 때
func pay(user : String, amount : Int){

}
// 클로저로 썼을 때
let payment = {(user : String, amount : Int) in

}
```


## 값을 캡쳐한다?
클로저는 특정 문맥의 상수나 변수의 값을 캡쳐할 수 있다.
즉, 원본이 사라져도 그 값을 활용할 수 있도록 만들어 준다.<br>
body안에서 다른 함수를 호출하는 것으로 사용할 수 있다.


## 후위 클로저
함수의 마지막 인자로 클로저를 넣고, 그 클로저의 길이가 길때 후휘 클로저를 사용할 수 있다.
```
someFunctionThatTakesAClosure(){
    // trailing code
}
```

## 이스케이핑 클로저
* 메서드의 실행이 종료된 후 실행되는 클로저
* 함수 밖에서 사용되거나 비동기로 실행되거나 `completionHander`로 사용되는 클로저는 파라미터 앞에 `@escaping` 키워드를 써주어야한다.
```
var completionHandlers: [() -> Void] = []
func somFunctionWithEscapingClosure(completionHandler : @escaping () -> Void) {
    completionHandlers.append(completionHandler)
}
```
이때 `completionHandler`는 `someFunctionWithEscapingClosure`가 끝나야 처리된다. 이렇게 함수가 끝나고 실행되는 클로저에 `@escaping`이 붙지 않으면 오류가 발생한다.

