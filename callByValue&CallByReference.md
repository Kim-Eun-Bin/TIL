## call by value 와 call by reference의 차이

### call by value

함수가 호출될 때 메모리 공간 안에서는 임시의 공간이 생성됩니다. 그리고 함수가 종료되면 해당공간은 사라집니다.
함수 호출시 전달되는 변수의 값을 복사하여 함수의 인자로 전달되고, 여기서 복사된 인자는 함수 안에서 지역적으로 사용하는 변수를 말합니다.
JAVA의 경우 함수에 전달되는 인자의 데이터 타입에 따라서 (기본자료형 / 참조자료형 ) 함수 호출 방식이 달라집니다.

기본 자료형 : call by value 로 동작 (int, short, long, float, double, char, boolean)
참조 자료형 : call by reference 로 동작 (Array, Class Instance)

```
void swap(int num1, int num2)
{
    int temp = num1;
    num1 = num2;
    num2 = temp;
}
void main()
{
    int a = 20, b = 60;
    swap(a, b);
    printf("a: %d, b: %d", a, b);
}
```

### call by reference

함수가 호출될 때, 메모리 공간 안에서는 함수를 위한 별도의 임시 공간이 생성되고, 함수 종료시 사라집니다. call by reference 참조에 의한 호출방식은 함수 호출시 인자로 전달되는 변수의 레퍼런스를 전달합니다.
함수 안에서 인자의 값이 변경되면, 함수 호출시에 있던 변수들도 값이 바뀝니다.

```
void swap(int &num1, int &num2)
{
    int temp = num1;
    num1 = num2;
    num2 = temp;
}
void main()
{
    int a = 20, b = 60;
    swap(a, b);
    printf("a: %d, b: %d", a, b);
}
```
