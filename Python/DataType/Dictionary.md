## 딕셔너리 자료형
딕셔너리는 리스트나 튜플처럼 순차적으로 해당 요솟값을 구하지 않고 key를 통해 Value를 얻습니다. <br />
다음은 기본 딕셔너리의 모습입니다.

```
{Key1: Value1, Key2: Value2, Key3: Value3, ...}
```

Key와 Value의 쌍 여러 개가 {}로 둘러싸여 있습니다. 각각의 요소는 Key : Value의 형태로 이루어져 있으며 쉼표(,)로 구분합니다.

### 딕셔너리 추가, 삭제
- 딕셔너리 추가
```
>>> a = {1: 'a'}
>>> a[2] = 'b'
>>> a

{1: 'a', 2: 'b'}
```

- 딕셔너리 요소 삭제
```
>>> del a[1]
>>> a

{2: 'b'}
```

### 딕셔너리 사용법
- key를 이용해 Value 얻기
```
>>> grade = {1: 'a', 2: 'b'}
>>> grade[1]

'a'
```

### 주의사항
딕셔너리에서 Key는 고유한 값이므로 중복되는 Key값을 설정해 놓으면 하나를 제외한 나머지 것들이 모두 무시됩니다.

### 딕셔너리 함수

- keys()

keys() 함수는 딕셔너리의 Key만을 모아서 dict_keys 객체를 돌려줍니다.
```
>>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
>>> a.keys()

dict_keys(['name', 'phone', 'birth'])
```

- values()

values() 함수는 딕셔너리의 Value만을 모아서 dict_values를 돌려줍니다.
```
>>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
>>> a.values()

dict_values(['pey', '0119993323', '1118'])
```

- items()

items() 함수는 Key와 Value의 쌍을 튜플로 묶은 값을 dict_items 객체로 돌려줍니다.
```
>>> a.items()

dict_items(['name': 'pey', 'phone': '0119993323', 'birth': '1118])
```

- clear()

clear() 함수는 딕셔너리 안의 모든 요소를 삭제합니다.
```
>>> a.clear()

{}
```

- get()

get(x) 함수는 x라는 Key에 대응되는 Value를 돌려줍니다.
```
>>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
>>> a.get('name')

'pey'
```

- in

in을 사용하면 해당 Key가 딕셔너리 안에 있는지에 대한 상태를 bool 값으로 돌려줍니다.
```
>>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
>>> 'name' in a
True
```
