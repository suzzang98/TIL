# 클래스(클래스)와 구조체(struct)

## 클래스 (클래스)
클래스는 프로퍼티와 메서드로 구성되어있다.<br>
클래스는 객체지향적 언어에서 사용되는 것이며, 붕어빵을 만들 때의 "틀"이라고 생각하면 이해하기 쉽다.<br>
즉 여러개의 객체를 만들기 위해서 그것을 같은 형태로 찍어낼 수 있도록 한 것이다.
```
클래스 Car{
    let model : String
    let price : Int

    init(modelName : String, price : Int){
        self.model = modelName
        self.price = price
    }

    func drive() {

    }
}

// 클래스의 사용
var myCar = Car(madelName : "Kia", price : 100000)
myCar.drive()
```

## 구조체 (Struct)
구조체란 클래스와 비슷하게 프로퍼티와 메서드로 구성되어있고, 이것로 캡슐화를 할 수 있게 해주는 사용자 정의 타입이다.<br>
```
struct Car{
    var model : String?
    var price : Int?

    func drive() -> String {
        if let model = self.model{
            return "my car is \(model)"
        }else{
            return "i don't know my car's model"
        }
    }
}

// 클래스의 사용
var myCar = Car(model : "Kia")
print(myCar.drive())

```

## 클래스와 구조체의 차이점
언뜻보면 클래스와 구조체가 다른 점이 같아 보인다. 하지만 두개는 구조상에서도, 메모리를 불러오는 과정에서도 차이가 존재한다.

1. 생성자의 유무<br>
클래스는 생성자(initializer)를 필수로 가진다. 하지만 구조체는 생성자를 정의하지 않으면 구조체가 자동으로 생성자를 제공한다.
2. 상속<br>
클래스는 상속이 가능해서 메소드나 프로퍼티를 다른 클래스로부터 상속받아서 사용할 수 있다.<br>
하지만 구조체는 상속이 불가능하다. 
3. 데이터의 전달 방식<br>
클래스는 데이터를 전달할 때 메모리의 <strong>위치</strong>를 전달한다. 따라서 힙에 레퍼런스를 저장하여 사용할 때에 적합하다.<br>
구조체는 데이터를 전달할 때 값을 <strong>복사</strong>하여 전달한다. 다라서 데이터가 중간에 수정될 위험이 없기에 비동기 처리를 할 때 적합하다.