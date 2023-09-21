# MVVM 패턴
MVVM 패턴이란 Model - View - ViewModel의 약자로, 프로젝트를 보다 모듈화되고 테스트가 쉬운 구조로 만들며, 규모가 큰 프로젝트도 상대적으로 관리하기 좋은 구조입니다.<br>
Model은 프로그램에서 사용되는 데이터를 저장하고, 데이터를 다루는 비즈니스 로직을 가지고 있는 요소입니다.<br>
그리고 View는 사용자에게 보일 화면을 표현하는 요소입니다.<br>
마지막으로 ViewModel은 Model과 View 사이의 매개체 역할을 수행하며, 데이터를 잘 가공하여 View에서 사용하기 쉬운 형태로 만들어줍니다.<br>
모든 View와 관련된 비즈니스 로직은 이곳 ViewModel에 들어가게 됩니다.<br>

### MVVM 패턴의 장단점
MVVM 패턴은 구성 요소를 엄격하게 분리하여, 유지 보수가 용이해지며 확장성이 향상되고, 각각의 구성 요소를 쉽게 테스트할 수 있다는 장점이 있습니다.<br>
그리고 데이터 바인딩을 통해 데이터와 UI 간의 동기화를 자동으로 처리해서 편리하고, 공통된 로직을 하나의 ViewModel로 만들어서 다양한 View와 공유할 수도 있기 때문에, 재사용성 측면에서도 좋다고 할 수 있습니다.<br>
하지만 ViewModel의 설계가 어렵기 때문에, 다른 아키텍처 패턴에 비해 학습 난이도가 높은 편이고, 작은 규모의 프로젝트에서 MVVM 패턴은 지나친 복잡성을 유발할 수 있다는 단점도 존재합니다.

### MVVM 패턴의 흐름
MVVM 패턴의 흐름은 이와 같습니다.<br>
1. 먼저 View로 사용자의 입력이 들어오면, View는 해당 이벤트를 ViewModel로 전달합니다.
2. ViewModel이 해당 이벤트에 대한 데이터를 Model에 요청하고, Model은 로컬 또는 서버에서 데이터를 가져와서 업데이트한 후, ViewModel에 데이터가 변경되었음을 알립니다.
3. ViewModel은 변경된 데이터를 가공하여 저장하고, View는 데이터바인딩을 통해 ViewModel을 관찰하고 있다가, 변화가 감지되면 자동으로 화면을 갱신합니다.
(* 참고: 2번 관련해서, 안드로이드에서는 데이터가 변경되었음을 알리는 과정을 주로 LiveData를 이용하여 구현합니다. LiveData는 생명 주기를 고려하여 데이터 변경을 관찰하고, 데이터가 변경될 때마다 Observer 객체(예: ViewModel)에 알려줍니다. ViewModel에서 Model의 데이터를 LiveData 객체로 래핑하여 데이터 변경 시 ViewModel이 변경사항을 알 수 있게 합니다.)
<br>
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/537aa20a-e099-4afb-b225-b3d03b981007)

<br>
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/11fce7f1-93df-47e5-ad45-224c80711ff5)
