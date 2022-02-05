## Overloading과 Overriding의 차이

### Overloading
같은 이름의 메서드 여러개를 가지면서 매개변수의 유형과 개수가 다르도록 하는 것을 말합니다.

```java
class Test{
    void testmethod(){
        System.out.println("매개변수 없음");
    }
    
    //매개변수 int형이 2개
    void testmethod(int a, int b){
        System.out.println("매개변수 :"+a+", "+b);
    }
    
    //매개변수 String형이 한 개
    void testmethod(String c){
        System.out.println("매개변수 : "+ c);
    }
    
}
 
public class OverLoadingTest {
 
    public static void main(String[] args) {
        
        //Test 객체 생성
        Test test = new Test();
        
        //매개변수가 없는 cat() 호출
        ot.testmethod();
        
        //매개변수가 int형 두개인 cat() 호출
        ot.testmethod(10, 70);
        
        //매개변수가 String 한개인 cat() 호출
        ot.testmethod("오버로딩");
        
    }
 
}
```
### Overriding
상위 클래스가 가지고 있는 멤버변수가 하위 클래스로 상속되는 것처럼 상위 클래스가 가지고 있는 메서드도 하위 클래스로 상속되어 하위 클래스에 사용할 수 있습니다.
또한, 하위 클래스에서 메서드를 재정의해서도 사용할 수 있는 것을 말합니다.

```java
class Parent{ //부모클래스
    public String name;
    public String phone;
    
    public void info(){
        System.out.println("이름은 " + name + ", 전화번호는 " + phone + "입니다.");
    }
    
}
 
class Children extends Parent{ // 부모 클래스를 상속
 
    int age;
    
    public void info() { // 부모클래스에 있는 info()메서드를 재정의
        super.info();
        System.out.println("나이는 " + age + "살 입니다.");
    }
}
 
public class OverTest {
 
    public static void main(String[] args) {
        
        // Parent 객체 생성
        Parent parent = new Parent();
        
        // 변수 설정
        parent.name = "유리";
        parent.phone = "010-1212-3434";
        parent.age = 20;
        
        // 호출
        parent.info();
        
    }
 
}
