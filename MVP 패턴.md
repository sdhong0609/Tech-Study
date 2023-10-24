# MVP 패턴
MVP 패턴이란 Model - View - Presenter의 약자로, MVC 패턴에서의 Model과 View 사이의 강한 의존성을 줄이기 위해서 나온 패턴입니다.<br>
Model은 프로그램에서 사용되는 데이터를 저장하고, 데이터를 다루는 비즈니스 로직을 가지고 있는 요소입니다.<br>
그리고 View는 사용자에게 보일 화면을 표현하는 요소입니다.<br>
마지막으로 Presenter는 Model과 View 사이의 중간 매개체 역할을 하며, View에서 요청한 정보를 Model로부터 가져온 다음, 가공해서 View로 전달하는 요소입니다.<br>
안드로이드에서는 일반적으로 인터페이스를 사용하여, View와 Presenter 사이에 느슨한 결합을 유지합니다.<br>

### MVP 패턴의 장단점
MVP 패턴의 가장 큰 장점은 Model과 View 사이의 의존성을 낮추어, MVC 패턴에 비해 유지보수가 용이해지고 확장성이 좋아진다는 것입니다.<br>
그리고 UI부분과 데이터 부분이 확실히 나뉘어져서, 각자가 해야 할 일이 명확해지고, 그 결과 코드가 매우 깔끔해집니다.<br>
하지만 View와 Presenter가 1:1 관계이기 때문에, 앱이 복잡해질수록 서로 간의 의존성이 강해지고, View가 많아질수록 Presenter 클래스의 개수도 많아진다는 단점이 있습니다.


### MVP 패턴의 흐름
MVP 패턴의 흐름은 이렇습니다.
1. 먼저 View로 사용자의 입력이 들어오면, View는 해당 이벤트를 Presenter에 전달합니다.
2. Presenter가 해당 이벤트에 대한 데이터를 Model에 요청하고, Model은 로컬 또는 서버에서 데이터를 가져와서 업데이트한 후, Presenter에 요청받은 데이터를 응답합니다.
3. Presenter가 전달받은 데이터를 가공하여 View에 전달하면, View는 그것을 기반으로 화면을 업데이트합니다.
<br>
<br>

![image](https://github.com/sdhong0609/Tech-Study/assets/78577085/1f7b34c2-680a-4d16-983f-13919df9c9d5)
