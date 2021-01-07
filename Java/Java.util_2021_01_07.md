# java.util

 Java 프로그래밍에 유용한 클래스들을 모아둔 것으로 대표적인 클래스로는 날짜와 관련된 Date, Calendar 가 있으며, 자료구조와 관련된 Collection 프레임워크 관련 클래스들이 포함되어 있음

### Calendar, Date

날짜와 시간에 관련한 데이터를 처리하는 클래스

> JDK1.0에서는 Date클래스를 사용하였으나, JDK1.1에서부터 향상된 기능을 추가한 Calendar클래스 이용



# Date 클래스

`Date()`생성자를 이용하여 객체를 생성
현재 시스템의 시간으로 객체를 만듦

```java
Date date = new Date();
```



# Calendar 클래스

추상클래스로서 직접 객체를 생성하지 않음

```java
Calendar c = Calendar.getInstance();
```

### 주요 멤버필드

`static int DATE` -  달의 날을 나타냄
`static int DAY_OF_MONTH` -  달의 날을 나타냄 (DATE와 동일)
`static int DAY_OF_WEEK` -  요일을 나타냄
`static int HOUR` -  오전 또는 오후의 몇 시인지를 나타냄
`static int HOUR_OF_DAY` -  시간을 나타냄
`static int MILLISECOND` -  밀리 초를 나타냄
`static int MINUTE` -  분을 나타냄
`static int MONTH` -  달을 나타냄
`static int SECOND` -  초를 나타냄
`static int YEAR` -  해를 나타냄



# Random

`Math.random()`과 유사
종자 값을 설정하여 난수를 발생시키는데, `System.currenttimeMilis()`로 해서 종자 값이 같을 수가 없음

`nextInt()` -  int형의 난수 발생
위와 같이 next다음에 자료형을 붙혀 원하는 자료형 난수를 구할 수 있음



# Scanner

화면, 파일, 문자열과 같은 입력 소스로부터 문자데이터를 읽어오는데 도움을 주기 위해 java1.5버전부터 추가됨

> 유사한 클래스로는 `StringTokenizer`가 있음

### 생성자

`Scanner(File source)`  -  지정된 파일로부터 스캔된 값을 생성하는 새로운 Scanner를 구축
`Scanner(InputStream source)`  -  지정된 입력 스트림으로부터 스캔된 값을 생성하는 새로운 Scanner를 구축

### 예시

```java
String input="1 fish 2 fish red fish blue fish"; // fish가 구별자 역할을 함
Scanner s = new Scanner(input).useDelimiter("\\s*fish\\s*"); // fish를 중심으로 앞과 뒤에 공백이 있음
System.out.println(s.nextInt()); // 1
System.out.println(s.nextInt()); // 2
System.out.println(s.next()); // red
System.out.println(s.next()); // blue
s.close();
```

> `useDelimiter`를 이용해 복잡한 형태의 구분자도 처리가 가능