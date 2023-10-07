# 코루틴 (Coroutines)
코루틴은 일종의 프로그래밍 개념으로 안드로이드와 코틀린에만 있는 개념이 아닙니다.<br>
일반적으로 많이 구현하는 서브 루틴은 단일 지점에서 시작되고 특정 지점에서 종료됩니다.<br>
하지만 코루틴은 단일 지점에서 시작하고 특정 지점에서 종료되는 것은 서브루틴과 동일하지만, 임의 지점에서 멈출 수 있고 해당 지점에서 재개할 수 있다는 것이 차이점입니다.<br>
안드로이드에서의 코루틴은, 비동기적으로 실행되는 코드를 간소화하기 위해 사용하는, 동시 실행 설계 패턴입니다.<br>
(* 참고 : 프로그래밍에서 루틴은 특정한 일을 처리하기 위한 일련의 명령 혹은 처리과정을 말합니다.)

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/90485713-550c-4013-97e4-a806aa9168ab)

<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/ddd14c65-b6d5-4f28-80cb-225aa4ede6a5)

<br>

### 코루틴 내부 동작 원리
suspend 함수는 JVM 상에서 suspend 키워드는 빠지고 continuation 파라미터가 추가됩니다.<br>
그리고 switch-case 문으로 label 변수를 설정하여 제어합니다.<br>
초기 label 값은 0이므로 case가 0인 경우의 코드를 실행하고, state machine에는 label을 1로 변경하고 현재의 상태값들을 저장한 다음, continuation으로 state machine을 넘겨줍니다.<br>
그리고 코드를 재개할 때, continuation으로 넘겨받은 state machine에 저장된 상태값들을 기반으로 코드를 다시 재개합니다.<br>
이 때 label 값이 1인 상태이기 때문에 case가 1인 경우의 코드를 실행합니다.<br>
코루틴은 내부적으로 이러한 방식을 통해 중단과 재개를 반복하며 동작합니다.<br>
(* 코루틴 내부 동작 원리 참고 영상 : https://youtu.be/usaD7HyN598?si=LP5VVVJTlcKm7S9K&t=1420 - 23:40부터)<br>
(* 참고 사이트 : https://tech.wonderwall.kr/articles/CoroutineDeepDive/)

### Continuation
Continuation은 프로그램의 제어 상태를 추상적으로 표현한 것입니다.<br>
코루틴에서 Continuation은 중단된 지점의 실행 상태와, 나중에 해당 지점에서 코드를 재개할 수 있는 정보를 저장하는데 사용됩니다.<br>

### CPS (Continuation Passing Style)
CPS란 Continuation Passing Style의 약자로, 호출되는 함수에 Continuation을 전달하고, 함수의 작업이 완료되는 대로 전달받은 Continuation을 호출하는 방식을 의미합니다. 이러한 의미에서 Continuation을 일종의 콜백으로 생각할 수 있습니다.<br>
("호출되는 함수에 Continuation을 전달하고" -> 코드상에서 continuation 파라미터가 추가된 것을 의미)<br>
("함수의 작업이 완료되는 대로 전달받은 Continuation을 호출하는 방식" -> 코드상에서 예를 들어 case가 0인 경우의 코드를 실행하고 완료하면, Continuation을 호출하여 상태값들이 저장된 state machine을 넘겨주는 것을 의미)
