# java.lang

JAVA 프로그래밍에 필요한 가장 기본적인 클래스들이 모여있는 패키지이다. import구문으로 호출해야 사용할 수 있는 다른 패키지들과는 달리 lang패키지는 import구문 없이도 자동으로 프로그램에 포함



# String

문자열을 저장하기 위해 문자열 배열 변수를 인스턴스 변수로 정의해 놓음
생성자 생성시 매개변수로 받는 문자열은 문자열 배열에 저장되는 것
다른 언어에서는 char형의 배열을 다루지만 자바에서는 문자열을 위한 클래스 제공

```
String a = "Happy Java" // 두개가 같음
String a = new String("Happy Java");
```

### 주요메서드

`char charAt(int index)` -  지정된 인덱스의 문자를 반환
`int compareTo(String anotherString)` - 2개의 char 라인을 사전적으로 비교 (같은지 다른지)
`int compareTolgnoreCase(String str)` -  대문자와 소문자의 구별 없이 2개의 char 라인을 사전적으로 비교 (같은지 틀린지)
`String concat(String str)` -  지정된 char 라인을 이 char 라인의 마지막에 연결

> `+`연산을 통해 할 수 있어 많이 쓰이지는 않음

`boolean startsWith(String prefix, int toffset)` -  이 char 라인이, 지정된 접두사로 시작될지 아닐지
`boolean endsWith(String suffix)` -  이 char 라인이, 지정된 접미말로 끝날지 아닐지
`boolean equals(Object anObject)` -  이 char 라인과 지정된 object를 비교
`boolean equalsIgnoreCase(String anotherString)` -  대문자와 소문자를 구별하지 않고, String을 다른 String과 비교
`byte[] getBytes()` -  객체를 바이트 배열로 반환해 줌
`byte[] getBytes(String charsetName)` -  객체를 charsetName에 설정한 글꼴 형태의 byte 배열로 변환`boolean isEmpty()` -  길이가 0인 경우에만 true 반환
`int lastIndexOf(int ch)` -  char 라인 내에서 마지막에 출현하는 위치의 인덱스 반환
`int length()` -  char라인의 길이를 반환
`String[] split(String regex)` -  char 라인을 지정된 정규 표현에 일치하는 위치에서 분할
`String substring(int beginIndex, int endIndex)` -  char 라인의 부분 char 라인인 char 라인을 반환 (자름)
`char[] toCharArray()` -  char라인을 새로운 char배열로 반환
`String toLowerCase()` -  String내의 모든 char를 소문자로 변환
`String toUpperCase()` -  String내의 모든 char를 대문자로 변환
`String trim()` -  선두와 말미의 공백을 삭제 후 반환



# StringBuffer

문자열을 추가하거나 변경할 때 주로 사용하는 자료형
(`StringBuilder`라는 것도 있으니 참고하면 좋음)

> String은 불변적인 객체, 길이가 제한되어 있음
> String의 내용을 바꾸려고 하려면 기존 객체를 버리고 새로운 객체를 생성해야 함

### 생성자

`StringBuffer()` -  초기용량이 16인 캐릭터 라인 버퍼를 구축
`StringBuffer(CharSequence seq)` -  지정된 CharSequence인수와 같은 char를 포함한 char 라인 버퍼를 구축
`StringBuffer(int capacity)` -  지정된 초기 용량을 가지는 char 라인 버퍼를 구축
`StringBuffer(String str)` -  지정된 char 라인의 내용에 초기화된 char 라인 버퍼를 구축

### 주요메서드

`StringBuffer append()` -  문자열을 추가
`StringBuffer insert()` -  문자열을 삽입



*<u>그밖에도 `math`, `wrapper`등등 많은 것이 있으니 참고하면 좋음</u>*