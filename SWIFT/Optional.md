# OPTIONAL(옵셔널)

## 옵셔널이란?
옵셔널은 어떤 변수를 저장할 때, 그 공간에 <strong>값이 없을 수도 있을 때</strong> 사용한다.
* 옵셔널로 랩핑한 값을 언랩핑해서 값에 접근할 수 있다.
* 값이 전혀 없다



## 옵셔널의 사용방법
* ?를 사용
* 값이 있다면 그 값을 반환하고, 값이 없다면 `nil`을 반환한다.

### nil?
값이 없음을 뜻한다.
-> 특정 타입에 대한 값의 부재를 표현한다.

## 옵셔널 바인딩
* 옵셔널 값이 빈 값인지 아닌지를 검사하고, 다른 변수에 대입해서 바인딩하는 것을 의미한다.
* `if let`, `if var`, `guard let`, `guard var`를 통해서 바인딩 가능하다.<br>
** 이것은 강제 언랩핑해주는 것보다 안전하다.

<code>
let roomNumber : Int? = nil
if let room = roomNumber {
    print(room)
}
// 출력값 없음
</code>

<code>
let roomNumber : Int? = 3
if let room = roomNumber {
    print(room)
}
// 출력값 3
</code>

## 옵셔널 강제 언래핑
* !를 사용하여 강제로 옵셔널 추출
* 강제 언래핑을 잘못 사용하면 프로그램이 비정상적으로 종료되기 때문에 주의해야함
<code>
let address : String? = nil
print(address!)
//에러 메세지 출력
</code>

## 옵셔널 체이닝
옵셔널을 체인처럼 연쇄적으로 사용하는 것을 말한다.<br>
`.`을 통해서 내부 프로퍼티나 매서드에 연속적으로 접근할 때 `?`를 사용하여 접근 가능하다.

<code>
struct Car{
    var name: String
    var owner: Person
}

struct Person{
    var who: String
    var address: String
}

let K5: Car? = Car(name: "k5", owner: Person(who: "suzzang_g", address: "Korea"))

print(K5.owner.address)
// 에러 - 옵셔널 값이 있다면 접근할 때도 써야한다.

print(K5?.owner.address)
// 이렇게 써야함!

</code>
