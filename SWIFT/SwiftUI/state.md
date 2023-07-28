# @State
상태 프로퍼티라고 하며, 레이아웃의 현재 상태를 저장하기 위해서 사용한다.
간단한 `String`, `Int` 같은 타입을 저장하기 위해서 사용되고, `@State` 프로퍼티 래퍼를 사용해서 선언할 수 있다.

-애플 공식문서의 사용 예-
```
struct PlayButton: View {
    @State private var isPlaying: Bool = false // Create the state.


    var body: some View {
        Button(isPlaying ? "Pause" : "Play") { // Read the state.
            isPlaying.toggle() // Write the state.
        }
    }
}
```
즉, 상태 프로퍼티가 변경되었을 때 그 프로퍼티가 선언된 뷰의 계층 구조를 다시 렌더링 해야한다고 `SwiftUI`가 마킹해놓은 것이다.
-> 바뀐 프로퍼티가 의존하고 있던 모든 뷰를 업데이트한다.
