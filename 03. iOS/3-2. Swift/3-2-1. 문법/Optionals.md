# Swift 문법

<br/><br/>

# Optionals
> "값이 없음"을 표현하는 옵셔널에대해 알아보고, <br/> 값이 없음을 나타내는 값인 nil과 옵셔널 형식에 저장된 값을 추출하는 방법에대해 작성된 문서입니다.

옵셔널 타입은 값이 없음 을 나타내는 nil을 사용하기 위해 선언하고 선언은 두가지가 잇는데 Type뒤에?를 적어주는것과
optionals < Tyep > (실제로는 띄어쓰기 안함) 풀코드로 선언할 수 있다. 

# Unwrapping
변수에 옵셔널을 적용하면 값(123)을 프린트 할때 optionals(123) 이라고 출력되는데
이를 강제 추출 하기 위해서는 변수뒤에!를 적어주면 된다.

```SWIFT
var num: Int? = 123

print(num)   //Optionals123 출력됨
print(num!)  //123 출력됨

```

# Optional Binding
#### 예제
```SWIFT
if let name: Type = OptionalExpression {
    statements
}
-----------------------------------------------------
while let name: Type = OptionalExpression {
    statements
}
-----------------------------------------------------
guard let name: Type = OptionalExpression else {
    statements
}

```
#### 예시
```SWIFT
var num: Int? = 123
if let n = num {
    print(n)
}
--------------------------------------------
var str: String? = "Swift"
guard let str else {
    fatalError()
}
```