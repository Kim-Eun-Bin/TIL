## if문
주어진 조건을 판단한 후 그 상황에 맞게 처리해야 할 경우를 위해 사용하는 것이 바로 if문 입니다.
```
>>> check = True
>>> if check:
      print("true")
    else:
      print("false")

true
```

### 들여쓰기
if문을 사용할 때는 if문에 속하는 모든 문장에 들여쓰기를 해줍니다.

### and, or, not

<img src="https://user-images.githubusercontent.com/56482682/150786322-60325f36-27ed-4b57-8cd9-38d1134b75a4.png" width="320" height="150" />

### elif
파이썬에서는 다중 조건 판단을 가능하게 하는 elif가 있습니다.
```
>>> pocket = ['paper', 'cellphone']
>>> card = True
>>> if 'money' in pocket:
      print('택시 이용')
    elif card:
      print('택시 이용')
    else:
      print('도보')

택시 이용
```

### 조건부 표현식

```
if score >= 60:
   message = "sucess"
else:
  message = "failure"
```
조건부 표현식을 사용하면 위의 코드를 더 간단하게 표현할 수 있습니다.
```
message = "success" if score >= 60 else "failure"
```

조건부 표현식은 다음과 같이 정의합니다.
```
조건문이 참인 경우 if 조건문 else 조건문이 거짓인 경우
```


