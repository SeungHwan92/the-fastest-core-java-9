# the-fastest-core-java-9
[가장 빨리 만나는 코어 자바 9] 같이 읽자!

3.4 람다 표현식
람다의 첫 등장!  (String first, String second) -> first.length() - second.length();

3.5
 <https://palpit.tistory.com/675/> "메서드 참조와 생성자 참조"

3.7
1. 람다 표현식의 유효 범위
지역 범위와 이름이 같은 매개변수를 선언 하는 것은 규칙에 어긋난다
EX)
``` java
int first = 0;
Comparatort<String> comp = (first, second) -> first.length() - second.length();

for(String arg: agrs){
new Thread(() -> Systome.out.println(arg)).start();
//arg를 캡처 할수 있다
```
i 변수의 유효 범위가 전체 루프이기 때문에 캡처 X , arg 변수는 반복 할 때마다 생성하기 때문에 캡처 O

3.8 
- 고차함수란
  함수를 인자로 전달 받거나 함수를 결과를 함수로 반환하는 함수
  
 ```java
 pubilc static Comparator<String> compareInDirection(int direction){
  return (x,y) -> direction * x.compareTo(y);
 }
 ```
 compareIndirection(1) -> 오름차순
 compareIndirection(-1) -> 내림차순

4.? EUNM 열거
eunm name 값으로 찾을 때 valueOf 사용
``` java
public Optional<NotificationEvent> test(String sendType){
        Optional<NotificationEvent> possible = Enums.getIfPresent(NotificationEvent.class, sendType);
        if (!possible.isPresent()) {
            throw new IllegalArgumentException("? There is no such planet!");
        }
        System.out.println(possible.get().name());
        return possible;
    }

    public NotificationEvent test2(String sendType){
        NotificationEvent possible = NotificationEvent.valueOf(sendType);
        NotificationEventDetail notificationEventDetail = NotificationEvent.valueOf(NotificationEventDetail.class, sendType);
        System.out.println(notificationEventDetail.name());
        if (possible == null) {
            return NotificationEvent.NONE;
        }
        System.out.println(possible.name());
        return possible;
    }
```
