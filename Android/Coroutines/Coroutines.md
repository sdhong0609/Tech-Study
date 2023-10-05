# 코루틴 (Coroutines)
코루틴은 일종의 프로그래밍 개념으로 안드로이드와 코틀린에만 있는 개념이 아닙니다.<br>
일반적으로 많이 구현하는 서브 루틴은 단일 지점에서 시작되고 특정 지점에서 종료됩니다.<br>
하지만 코루틴은 단일 지점에서 시작하고 특정 지점에서 종료되는 것은 서브루틴과 동일하지만, 임의 지점에서 멈출 수 있고 해당 지점에서 재개할 수 있다는 것이 서브루틴과의 차이점입니다.<br>
안드로이드에서의 코루틴은 비동기적으로 실행되는 코드를 간소화하기 위해 사용할 수 있는 동시 실행 설계 패턴입니다.<br>
(* 참고 : 프로그래밍에서 루틴은 특정한 일을 처리하기 위한 일련의 명령 혹은 처리과정을 말합니다.)

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/90485713-550c-4013-97e4-a806aa9168ab)

<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/ddd14c65-b6d5-4f28-80cb-225aa4ede6a5)

<br>
<br>

### Continuation
Continuation은 프로그램의 제어 상태를 추상적으로 표현한 것입니다.<br>
코루틴에서 Continuation은 코루틴이 중단된 지점의 실행 상태와 나중에 해당 지점에서 코드를 재개할 수 있는 정보를 저장하는데 사용됩니다.<br>
(* 코루틴 내부 동작 원리 참고 영상 : https://youtu.be/usaD7HyN598?si=LP5VVVJTlcKm7S9K&t=1420 - 23:40부터)
