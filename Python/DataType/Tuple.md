## 튜플 자료형
튜플은 몇 가지 점을 제외하면 리스트와 거의 비슷하며 리스트와 다른 점은 다음과 같습니다. <br />

- 리스트는 []으로 둘러싸지만 튜플은 ()로 둘러쌉니다.
- 리스트는 그 값의 생성, 삭제, 수정이 가능하지만 튜플은 값을 바꿀 수 없습니다.

```
>>> t1 = ()
>>> t1 = (1, )
>>> t3 = (1, 2, 3)
>>> t4 = 1, 2, 3
>>> t5 = ('a', 'b', ('ab', 'cd))
```
리스트와 모습은 거의 비슷하지만, 튜플에서는 1개의 요소만을 가질 때에는 요소 뒤에 콤마(,)를 반드시 붙여야 하며 괄호()를 생략해도 무방합니다.

### 튜플의 수정 삭제 에러
```
>>> t1 = (1, 2, 'a', 'b')
>>> t[0] = 'c' // t[0] 수정 시도
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object doesn't support item assignment // Type error
```
```
>>> t1 = (1, 2, 'a', 'b')
>>> del t[0] // t[0] 삭제 시도
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object doesn't support item deletion // Type error
```

### 튜플 다루기
- 인덱싱
```
>>> t1 = (1, 2, 'a', 'b')
>>> t1[0]

1
```
- 슬라이싱
```
>>> t1 = (1, 2, 'a', 'b')
>>> t1[1:]

(2, 'a', 'b')
```
- 더하기
```
>>> t2 = (3, 4)
>>> t1 + t2

(1, 2, 'a', 'b', 3, 4)
```
- 곱하기
```
>>> t2 * 3

(3, 4, 3, 4, 3, 4)
```
- 길이
```
>>> t1 = (1, 2, 'a', 'b')
>>> len(t1)

4
```
