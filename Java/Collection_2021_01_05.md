# Collection

여러 원소들을 담을 수 있는 자료구조

멤버 객체들을 제어, 관리 하기 위한 클래스
배열과 같이 멤버 객체를 관리하기 위한 클래스들
(사용하는 목적은 배열과 같지만, 제공하는 기능은 더 많음)

> Collection Object : 여러 개의 요소를 묶어 하나의 객체로 만든 것
> Collection Framework : 컬렉션 클래스들과 인퍼페이스들의 집합을 통틀어 일컫는 말

배열은 정적 메모리 할당이지만, Collection은 동적 메모리 할당을 함
-> 필요한 만큼 계속 추가 가능

<img src="https://blog.kakaocdn.net/dn/bYhwrV/btqB2HKUB51/LxvcsJqFvgsVRTUm6U4kQ1/img.png" alt="img" style="zoom:100%;" />

# 핵심 인터페이스

- **`java.util.List`**
  순서가 있는 데이터의 집합
  데이터의 중복을 허용
  가변길이름 가짐

- **`java.util.Set`**
  순서를 유지하지 않는 데이터의 집합
  데이터의 중복을 허용하지 않음

- **`java.util.Map`**
  순서는 유지되지 않는 키와 값의 쌍으로 이루어진 데이터의 집합
  (key값을 통해 key와 연결된 객체들을 관리)

  키(key)는 중복을 허용하지 않음
  값(value)은 중복을 허용



# HashSet

### 생성자

`HashSet()` -  디폴트의 초기 용량(16) 및 부하 계수 (0.75)를 가짐
`HashSet(int initialCapacity)` -  지정된 초기 용량 및 디폴트의 부하 계수를 가짐
`HashSet(int initialCapacity.float loadFactor)` -  지정된 초기 용량 및 지정된 부하 계수를 가짐

무한한 데이터의 집합이지만, 모든 공간을 차지할 수 없으니 초기 용량을 지정함
어느정도(부하계수) 차면 다시 용량을 확보

### 주요 메서드

`boolean add(E e)` - 지정된 요소가 세트의 요소로서 존재하지 않는 경우 그 요소를 세트에 추가
`void clear()` -  모든 요소를 세트로부터 삭제
`boolean contains(Object o)` -  지정된 요소가 세트에 포함되어 있는 경우에 true
`boolean isEmpty()` -  이 세트에 요소가 1개도 포함되지 않은 경우에 true
`Iterator<E> iterator()` -  세트내의 각 요소에 대한 Iterator를 반환

> 자바의 컬렉션 프레임웍에서 컬렉션에 저장되어 있는 요소들을 읽어오는 방법을 표준화 하였는데
> 그 중 하나가 Iterator

`boolean remove(Object o)` -  지정된 요소가 이 세트에 존재하는 경우에, 요소를 삭제

```java
import java.util.*;
public class Main {
    public static void main(String[] args){
        HashSet hs = new HashSet();
        String a = new String("유재석");
        String b = "강호동";
        hs.add(a);
        hs.add(b);
        System.out.println("인원 : "+hs.size());
        hs.remove("강호동");
        System.out.println("인원 : "+hs.size());
        hs.clear();
        System.out.println("인원 : "+hs.size());
    }
}
```



# HashMap

### 생성자

`HashMap()` -  디폴트의 초기 용량(12) 및 부하 계수 (0.75)를 가짐
`HashMap(int initialCapacity)` -  지정된 초기 용량 및 디폴트의 부하 계수를 가짐
`HashMap(int initialCapacity.float loadFactor)` -  지정된 초기 용량 및 지정된 부하 계수를 가짐

`HashSet`과 비슷하지만, 값만 넣던 것과 달리 키값과 값 둘다 넣어야 함

### 주요 메서드

`void clear()` -  모든 매핑을 Map으로부터 삭제
`boolean containKey(Object key)` -  지정된 키의 매핑이 Map에 포함되어 있는 경우 true
`boolean containValue(Object value)` -  Map이 1개 또는 복수의 키가 지정된 값에 매핑하고 있을 경우에 true
`V get(Object key)` - 지정된 키가 Map 되고 있는 값을 돌려줌 (없으면 null)
`boolean isEmpty()` -  Map이 키와 값의 매핑을 보관 유지하고 있지 않을 경우에 true
`Set <K> keySet()` - Map에 포함되는 키 Set뷰를 돌려줌 (키값만 보여줌)
`V put(K key, V value)` - 지정된 값과 지정된 키를 Map에 저장
`V remove(Object key)` -  지정된 키의 매핑이 있으면 Map으로부터 삭제
`boolean remove(Object key, Object value)` -  지정된 값으로 지정된 키가 현재 매핑되고 있는 경우에만, 그 키의 엔트리를 삭제
`int size()` -  Map내의 매핑의 수를 돌려줌

```java
import java.util.*;
public class Main {
    public static void main(String[] args){
        HashMap map = new HashMap();
        map.put("야구선수", "류현진");
        map.put("야구선수", "추성훈"); // 기존에 있는 류현진은 없어짐(덮힘)
        map.put("축구선수", "기성용");
        map.put("농구선수", "서장훈");
        System.out.println("개수 : "+ map.size());
        Object name = map.get("축구선수");
        System.out.println("축구선수 : "+name);
    }
}
```



