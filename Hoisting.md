# Hoisting(호이스팅)

## The behaviour of Javascript syntax which allows variables to be used before they are declared

- 즉, 자바스크립트 문법에서 변수나 함수를 선언 이전에 사용할 수 있다는 뜻.
- 호이스팅은 정말 변수나 함수가 위로 끌어올려지는 것이 아니고, 변수나 함수를 선언 이전에 사용할 수 있기 때문에 끌어 올려지는 것처럼 보이는 것일 뿐이다.

## 그럼 어떻게 선언 이전에 사용할 수 있나?

- 실행컨텍스트가 생성될 때, 변수 객체에 배열 식별자 정보를 담는 variable 배열에 변수들을 먼저 담는다.
- 먼저 담기때문에 선언을 나중에 해도 사용이 가능한 것이다.

## var 와는 달리 const나 let은 어떻게 호이스팅 되지 않고 TDZ(Temporal Dead Zone)에 들어가는 것인가?

- TDZ: 선언 전에 변수를 사용하는 것을 비 허용하는 개념상의 공간.
- var는 선언과 동시에 AllocateTo 메소드를 통해 메모리에 바로 할당이 된다.
- 하지만 const나 let은 set_initializer_position 메소드를 통해 해당 코드의 position을 정해주어 초기화 해주는 과정을 거친다.
- var와는 달리 메모리 할당 이전에 일종의 방어코드가 추가됨으로써, 선언은 되어 있지만 변수에 값을 담기 위한 메모리에 공간이 확보되지 않은 상태가 되는 것이다.
- 즉, const나 let 또한 동일하게 실행컨텍스트가 생성되는 시점에 variable 배열에 담겨 호이스팅이 되지만 일종의 초기화(set_initializer_position)로 인해 선언이나 할당 이전에 미리 사용할 수 없게 된것이다.