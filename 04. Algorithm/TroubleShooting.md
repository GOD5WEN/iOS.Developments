# Algorithm Test

* ## 2023/11 Troble Shooting 


<br/><br/>



--- 
<br/><br/>
 [두 수가 같으면 1 다르면 -1을 retrun하도록 함수를 완성해주세요.] (https://velog.io/@5wen/20231128)

<details>
<summary>접기/펼치기</summary>

<!-- summary 아래 한칸 공백 두어야함 -->
## 정답 코드
```SWIFT
     func solution(_ num1:Int, _ num2:Int) -> Int { 
    if num1 == num2 {
        return 1
    } else {
        return -1
    }
      }
```
 
</details> <br/><br/>


--- 
<br/><br/>  
[나이 age가 주어질 때, 2022년을 기준 출생 연도를 return 하는 함수를 완성해주세요.] (https://velog.io/@5wen/2023.11.27)

<details>
<summary>접기/펼치기</summary>

<!-- summary 아래 한칸 공백 두어야함 -->
## 정답 코드
```SWIFT
     import Foundation

     func solution(_ age:Int) -> Int {
   
     var year: Int = 2022
    
     return year-(age-1)
     }
```

</details> <br/><br/>