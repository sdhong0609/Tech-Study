# MVVM 패턴
MVVM 패턴이란 Model - View - ViewModel의 약자로, 소프트웨어 개발을 보다 모듈화되고 테스트가 쉬운 구조로 만들며, 큰 프로젝트도 상대적으로 관리하기 좋은 구조입니다.<br>
Model은 프로그램에서 사용되는 데이터를 저장하고, 데이터를 다루는 비즈니스 로직을 가지고 있는 요소입니다.
그리고 View는 사용자에게 보일 화면을 표현하는 요소입니다.
마지막으로 ViewModel은 View와 Model 사이의 매개체 역할을 수행하며, 데이터를 잘 가공해서 View에서 사용하기 쉬운 형태로 만들어주고, 모든 View와 관련된 비즈니스 로직은 이곳에 들어가게 됩니다.<br>
MVP 패턴과는 다르게 View와 ViewModel이 1:n의 관계를 가질 수 있으며, ViewModel은 View를 참조하지 않기 때문에 독립적입니다.

### MVVM 패턴의 장단점
MVVM 패턴은 Model과 View 사이, View와 ViewModel 사이의 의존성이 없기 때문에, 여러 개의 View가 하나의 ViewModel을 사용할 수 있고, 유닛 테스트가 더 쉬워진다는 장점이 있습니다.<br>
그리고 데이터 바인딩을 통해 View와 ViewModel 사이의 데이터 동기화를 자동으로 처리하고, 유연하고 확장 가능한 구조를 제공하여 UI와 비즈니스 로직의 확실한 분리를 촉진합니다.<br>
하지만 ViewModel의 설계가 어렵기 때문에, 다른 아키텍처 패턴에 비해 학습 난이도가 높은 편이고, 작은 규모의 프로젝트에서의 MVVM 패턴은 지나친 복잡성을 유발할 수 있다는 단점도 존재합니다.

### MVVM 패턴의 흐름
MVVM 패턴의 흐름은 이와 같습니다.<br>
1. 사용자의 입력을 View가 받은 다음, ViewModel로 사용자 입력을 전달합니다.
2. ViewModel은 Model에 데이터를 요청하고, Model은 ViewModel에 요청받은 데이터를 응답합니다.
3. ViewModel은 전달받은 데이터를 가공하여 저장하고, View는 데이터바인딩을 통해 ViewModel을 관찰하고 있다가, 변화가 감지되면 자동으로 화면을 갱신합니다.
<br>
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/537aa20a-e099-4afb-b225-b3d03b981007)

<br>
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/11fce7f1-93df-47e5-ad45-224c80711ff5)
