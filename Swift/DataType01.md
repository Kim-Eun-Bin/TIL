## 데이터 타입
데이터 타입은 프로그램 내에서 다뤄지는 데이터의 종류를 뜻합니다. <br />
swift의 모든 데이터 타입의 이름은 첫글자가 대문자로 시작하는 대문자 카멜케이스를 사용합니다.

### Int & UInt
정수타입입니다. Int는 +, - 부호를 포함한 정수를 의미하며 이 중 - 부호를 포함하지 않는 0을 포함한 양의 정수는 UInt로 표현합니다. <br />
Int와 UInt는 각각 8비트, 16비트, 32비트, 64비트의 형태를 갖고 있습니다. 32비트 아키텍쳐에서는 Int32가 Int타입으로, UInt32가 UInt 타입으로 저장됩니다. <br />
그리고 64비트 아키텍쳐에서는 Int64가 Int타입으로, UInt64가 UInt타입으로 저장됩니다. <br /><br />

각 진수에 따라 정수를 표현하는 방법은 다음과 같습니다.
- 10진수 : 평소에 쓰던 숫자와 동일하게 작성하여 표현합니다.
- 2진수 : 접두어 0b를 사용하여 표현합니다.
- 8진수 : 접두어 0o를 사용하여 표현합니다.
- 16진수 : 접두어 0x를 사용하여 표현합니다.

```
let decimalInteger: Int = 28
let binaryInteger: Int = 0b11100 // 2진수로 10진수 28
let octalInteger: Int = 0o34 // 8진수로 10진수 28
let hexadecimalInteger: Int = 0x1C // 16진수로 10진수 28
```

### Bool
Bool은 불리언 타입이며, 참(true) 또는 거짓(false)만 값으로 가집니다.
```
let boolean: Bool = true
```

### Float & Double
Float와 Double은 부동 소수점을 사용하는 실수형이며 부동소수 타입이라고 합니다. <br />
정수형보다 훨씬 넓은 범위의 수를 표현할 수 있습니다. swift에는 64비트의 부동소수 표현을 하는 Double과 32비트의 부동소수 표현을 하는 Float가 있습니다. <br />
64비트 환경에서 Double은 최소 15자리 십진수를 표현할 수 있고, Float는 6자리 십진수를 표현할 수 있습니다.
```
var floatValue: Float = 1234567890.1 // float의 범위를 넘어섭니다. 표현 가능한 만큼만 남기므로 정확도가 떨어집니다.
let doubleValue: Double = 1234567890.1 // double로 표현 가능합니다.

floatValue = 123456.1 // float이 표현 가능한 수로 변경합니다.
```

### Character
단어, 문장처럼 문자의 집합이 아닌 단 하나의 문자를 의미합니다. swift는 유니코드 문자를 사용하므로 모든 언어나 특수기호 등을 사용할 수 있습니다. <br />
문자를 표현하기 위해서는 값의 앞뒤에 큰따옴표를 붙여서 표현합니다. 
```
let alphabetA: Character = "A"

let commandCharacter: Character = "♡" // Character 값에 유니코드 문자를 사용할 수 있습니다.
```

### String
String은 문자의 나열, 즉 문자열입니다. Character와 마찬가지로 유니코드를 사용할 수 있으며, 값의 앞뒤에 큰따옴표를 붙여서 표현합니다.
```
let name: String = "KimEunBin"
let introduce: String = String()

introduce.append("my name is") // append()를 사용하여 문자열을 이어붙일 수 있습니다.
introduce = introduce + " " + name // 연산자를 사용하여 이어붙일 수 있습니다.

print(introduce) // my name is KimEunBin
```

### 특수문자
특수문자는 제어문자라고도 합니다. swift에는 일정 기능을 수행하는 특수문자가 있습니다.
- \n : 줄바꿈
- \\ : 문자열 내에서 백슬래시를 표현할 때 사용
- \" : 문자열 내에서 큰따옴표를 표현할 때 사용
- \t : 탭 문자. 키보드의 탭키를 눌렀을 때와 같은 효과
- \O : 문자열이 끝났음을 알리는 null 문자

### Any, AnyObject와 nil
Any는 swift의 모든 데이터 타입을 사용할 수 있다는 의미를 가집니다. <br />
변수 또는 상수의 데이터 타입이 Any로 저장되어 있다면 어떤 종류의 데이터 타입이든지 상관없이 할당될 수 있고, AnyObject는 클래스의 인스턴스만 할당할 수 있습니다. <br />
nil은 '없음'을 나타내는 키워드입니다. 변수 또는 상수에 값이 들어있지 않고 비어있음을 의미합니다.
