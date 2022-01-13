## 딕셔너리
딕셔너리는 요소들이 순서없이 키와 값의 쌍으로 구성되는 컬렉션 타입입니다. <br />
딕셔너리에 저장되는 값은 항상 키와 쌍을 이루는데, 딕셔너리 안에는 키가 하나이거나 여러개일 수 있습니다. <br />
단, 하나의 딕셔너리 안의 키는 그 안에서 유일해야 합니다. <br />
```
typealias StringIntDictionary = [String:Int]

// 키는 String, 값은 Int인 빈 딕셔너리 생성
var numberForName: Dictionary<String, Int> = Dictionary<String, Int>()
var numberForName: [String: Int] = [String: Int]() // 위의 선언과 동일한 표현

var numberForName: StringIntDictionary = StringIntDictionary() // 위와 동일
Var numberForName: [String: Int] = [:] // 타입을 명확히 명시했다면 [:] 만으로도 빈 딕셔너리 생성

Var numberForName: [String: Int] = [“eunbin”: 100, “Jenny”: 200] // 초깃값을 주어 생성

print(numberForName.isEmpty) // false
print(numberForName.count) // 2
```
딕셔너리는 각 값에 키를 통해 접근할 수 있습니다. 딕셔너리 내부에서 키는 유일해야 하며, 값은 유일하지 않습니다. <br />
딕셔너리는 배열과 다르게 내부에 없는 키로 접근해도 오류가 나지 않고, nil을 반환합니다.
- removeValue(forKey:) : 특정 키에 해당하는 값 제거

```
numberForName[“eunbin”] = 200
numberForName[“John”] = 100 // John이라는 키로 100 값 추가

numberForName.removeValue(forKey: “John”)) // John이라는 키에 해당하는 값 삭제
```
