# Wrapper 클래스

기본 타입의 데이터를 객체로 취급해야 하는 경우가 있을 때 기본 타입을 객체로 만들기 위해 사용하는 클래스
wrapper 클래스는 모두 java.lang 패키지에 포함되어 제공됨

> 기본 타입 : char, int, float, double, boolean

ex) 메서드의 인수로 객체 타입만 요구 -> 기본 타입의 데이터를 그대로 사용할 수 없음
	  (기본 타입의 데이터를 객체로 변환 후 작업해야 함)

| 기본 타입 |  래퍼 클래스  |
| :-------: | :-----------: |
|   byte    |     Byte      |
|   short   |     Short     |
|    int    |  **Integer**  |
|   long    |     Long      |
|   float   |     Float     |
|  double   |    Double     |
|   char    | **Character** |
|  boolean  |    Boolean    |

wrapper 클래스는 산술 연산을 위해 정의된 클래스가 아니여서, 인스턴스에 저장된 값을 변경할 수 없음
값을 참조하기 위해 새로운 인스턴스를 생성하고, 생성된 인스턴스의 값만을 참조할 수 있음



# 박싱, 언박싱

기본 타입의 데이터를 wrapper 클래스의 인스턴스로 변환하는 과정 -> **박싱**
wrapper 클래스의 인스턴스에 저장된 값을 기본 타입의 데이터로 꺼내는 과정 -> **언박싱**

![박싱과 언박싱](http://www.tcpschool.com/lectures/img_java_boxing_unboxing.png)

```java
Integer num = new Integer(17); // 박싱
int n = num.intValue(); // 언박싱
```

# 오토 박싱, 오토 언박싱

JDK 1.5부터 박싱과 언박싱이 필요한 상황에서 자바 컴파일러가 자동으로 처리해주는데 이렇게 자동화된 박싱과 언박싱을 **오토 박싱**, **오토 언박싱**이라 함

```java
Character ch = 'X'; // Character ch = new Character('X'); // 오토박싱
char c = ch; // char c = ch.charValue(); // 오토언박싱
```

