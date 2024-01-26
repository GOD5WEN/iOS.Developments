#### 1. **배열(Array)** *[ ]*
 배열(Array) 는 순서의 개념이다. 여러가지 변수를 나열 하면 나열된 순서로 데이터를 가져올 수 있다.

   ```SWIFT
   var fruits: [String] = ["Apple", "Banana", "Cherry"]
   fruits.append("Date")
   let firstFruit = fruits[0]  // Apple
   ```

#### 2. **집합(Set)** *< >*
 집합(Set)은 배열(Array)과 비슷하나, 순서의 개념이 없는 묶음이다. 

 ```SWIFT
 var colors: Set<String> = ["Red", "Green", "Blue"]
colors.insert("Yellow")
let isContainsRed = colors.contains("Red")  // true
```

#### 3. **사전(Dictionary)** *[키: 벨류]*
사전(Dictionary)은 "~는 ~이다" 처럼 대치되는 값 이다. 

키로 밸류에 접근하는 방법 이라고 표현한다.

```SWIFT
var capitals: [String: String] = ["Korea": "Seoul", "Japan": "Tokyo"]
capitals["China"] = "Beijing"
let koreanCapital = capitals["Korea"]  // Seoul
```