# Coroutine Context
Coroutine Context는 코루틴이 실행될 때 사용되는 실행 환경을 정의하는 요소입니다.<br>
코루틴 컨텍스트의 구성 요소들로는 Dispatchers, Job, CoroutineExceptionHandler 등이 있습니다.

### Dispatchers
Dispatcher는 코루틴이 실행되는 스레드를 지정하는 역할을 하며 용도에 따라 Main, IO, Default, Unconfined 중 적합한 Dispatcher를 사용할 수 있습니다.<br>
* Main은 메인 스레드에서 UI 관련된 변경을 해야 할 때 사용합니다.
* IO는 파일 I/O 혹은 네트워크 I/O 같은 입출력 작업을 처리하기에 적합합니다.
* Default는 CPU 연산을 많이 사용하는 작업에 적합합니다. 크기가 큰 리스트를 다루거나 필터링을 하는 등의 무거운 연산이 필요한 작업을 처리할 때 사용합니다.
* Unconfined는 다른 Dispatchers와 달리 특정 스레드를 지정하지 않으며, 일반적으로는 사용하지 않습니다.

### Job (+ Deferred)
코루틴이라는 추상적인 흐름을 Job이라는 객체로 만들어서 흐름을 제어할 수 있습니다.<br>
해당 코루틴이 실행 중인지, 완료되었는지, 취소되었는지를 추적할 수 있습니다.<br>
만약 코루틴의 작업이 완료되었을 때 결과를 반환받고 싶다면 Deferred를 사용하면 됩니다.<br>
Deferred는 결과값을 가지는 Job이기 때문에 Deferred는 Job이 가지고 있는 모든 특성을 동일하게 가집니다.

### CoroutineExceptionHandler
마지막으로 CoroutineExcpetionHandler는 코루틴에서 예외 처리하는 데 사용되는 인터페이스로, 이를 구현하여 예외 처리를 할 수 있습니다.

<br>

# Coroutine Builder
코루틴 빌더는 코루틴을 시작하고 관리하는 데 사용되는 여러가지 함수를 의미합니다.<br>
Job 객체를 반환하는 launch(), Deferred 객체를 반환하는 async(), Dispatcher를 스위칭하기 위한 withContext() 등이 있습니다.
