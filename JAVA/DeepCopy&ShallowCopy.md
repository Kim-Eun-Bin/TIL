## Deep copy 와 Shallow copy의 차이
객체의 복사는 크게 깊은 복사 (deep copy)와 얕은 복사 (shallow copy)로 나뉩니다.
두 개념의 차이를 간단하게 말하면 얕은 복사는 객체의 참조값(주소값)을 복사하고, 깊은 복사는 객체의 실제 값(value)를 복사합니다.

### Deep copy
객체를 복사 할 때, 해당 객체와 인스턴스 변수까지 복사하는 방식으로, 전부를 복사하여 새 주소에 담기 때문에 참조를 공유하지 않습니다.

### Shallow copy
객체를 복사할 때, 해당 객체만 복사하여 새 객체를 생성합니다. 복사된 객체의 인스턴스 변수는 원본 객체의 인스턴스 변수와 같은 메모리 주소를 참조합니다.
따라서, 해당 메모리 주소의 값이 변경되면 원본 객체 및 복사 객체의 인스턴스 변수 값은 같이 변경됩니다.

### Example

```java
public class CopiableObject {
  private String name;
  
  private int value;
  
  private String[] array;
  
  public CopiableObject(String name, int value, String[] array) { 
    this.name = name;
    this.value = value;
    this.array = array;   
 }
 
 public CopiableObject shallowCopy() {
    return new CopiableObject(this.name, this.value, this.array);
 }
 
 public CopiableObject deepColy() {
    return new CopiableObject(this.name, this.value, this.array);
 }
 
 public String getName() {
     return name;
 }
 
 public int getValue() {
    return value;
 }
 
 public String[] getArray() {
    return array;
 }
```
