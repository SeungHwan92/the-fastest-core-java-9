# the-fastest-core-java-9
[가장 빨리 만나는 코어 자바 9] 같이 읽자!

3.4 람다 표현식
람다의 첫 등장!  (String first, String second) -> first.length() - second.length();

3.7.1 람다 표현식의 유효 범위
지역 범위와 이름이 같은 매개변수를 선언 하는 것은 규칙에 어긋난다
EX)
``` java
int first = 0;
Comparatort<String> comp = (first, second) -> first.length() - second.length();
```
