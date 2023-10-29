# MVC 패턴
MVC 패턴은 프로그래밍에서 가장 널리 사용되는 구조 중 하나이며, Model - View - Controller의 약자입니다.<br>
Model은 프로그램에서 사용되는 데이터를 저장하고, 데이터를 다루는 비즈니스 로직을 가지고 있는 요소입니다.<br>
View는 사용자에게 보일 화면을 표현하는 요소이고, Controller는 사용자로부터 입력을 받고 처리하는 요소입니다.

### MVC 패턴의 장단점
MVC 패턴의 장점으로는 Model이 View와 Controller에 묶여있지 않아 재사용이 가능하다는 점이 있습니다.<br>
그리고 다양한 플랫폼에 적용할 수 있는 범용적인 패턴으로, 구현하기 쉽고 단순해서 개발기간도 짧아집니다.<br>
하지만 View가 UI 갱신을 위해 Model을 직/간접적으로 참조하여, Model과 View 사이에 의존성이 발생하므로, 앱이 커지고 로직이 복잡해질수록 유지보수가 힘들어진다는 단점이 있습니다.<br>
또한 앱이 커질수록 Controller에 많은 코드가 쌓여서, 문제가 발생할 가능성이 높아집니다.<br>
특히 안드로이드에서는 액티비티 혹은 프래그먼트가 View와 Controller를 둘다 갖고 있기 때문에, 하나의 클래스에서 너무 많은 로직을 처리해야 하는 문제가 발생합니다.<br>
그래서 일반적으로 안드로이드에서 MVC 패턴은 권장되지 않습니다.

### MVC 패턴의 흐름
통상적인 MVC 패턴의 흐름은 이렇습니다.
1. 사용자 입력이 Controller에 전달되면,
2. Controller는 사용자 입력에 해당하는 Model에 업데이트를 요청합니다.
3. Controller는 업데이트한 Model을 반영할 View를 선택하고, (Controller와 View는 1:n 관계로 하나의 Controller가 여러개의 View를 관리 가능)
4. View는 Model로부터 데이터를 가져와 화면을 업데이트합니다.

<br>
<br>

![image](https://github.com/sdhong0609/Tech-Study/assets/78577085/5ef435fa-a789-42aa-b9ef-4bcf7f178bd7)

