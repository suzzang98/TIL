# 클로저(Closure)
* 이름없는 함수, 코드블록 - 람다 함수와 비슷하다.
* 상수나 변수의 참조를 캡쳐해 저장할 수 있다.
* 비동기 처리가  필요할 때 사용할 수 있다.

```
// 함수로 썼을 때
func pay(user : String, amount : Int){

}
// 클로저로 썼을 때
let payment = {(user : String, amount : Int) in

}
```

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
