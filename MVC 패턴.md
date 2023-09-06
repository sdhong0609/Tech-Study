# MVC 패턴
MVC는 안드로이드와 관계없이 프로그래밍 시 가장 널리 사용되는 구조 중 하나이며 Model - View - Controller의 약자입니다.<br>
Model은 프로그램에서 사용되는 실제 데이터와, 데이터를 다루는 로직을 가지고 있는 요소입니다.<br>
View는 사용자에게 보일 화면을 표현하는 요소입니다.<br>
마지막으로 Controller는 사용자로부터 입력을 받고, 이를 Model에 의해 View 정의를 하는 요소입니다.

### MVC 패턴의 작동 순서
통상적인 MVC 패턴의 순서는 이렇습니다.
1. 사용자 입력이 Controller에 전달되면,
2. Controller는 사용자 입력에 해당하는 Model을 업데이트합니다.
3. Model의 상태가 변경되면 View에게 해당 변경 사항을 알리고,
4. View는 Model로부터 데이터를 가져와 화면을 업데이트합니다.

### MVC 패턴의 장단점
MVC 패턴의 장점으로는 Model과 View가 분리되어 있고, Model이 View와 Controller에 묶여있지 않아 재사용이 가능하다는 점이 있습니다.<br>
그리고 다양한 플랫폼에 적용할 수 있는 범용적인 패턴으로, 구현하기 가장 쉽고 단순하기 때문에 개발기간도 짧아집니다.<br>
하지만 View가 UI 갱신을 위해 Model을 직/간접적으로 참조하여 Model과 View 사이에 의존성이 발생하므로, 앱이 커지고 로직이 복잡해질수록 유지보수가 힘들어진다는 단점이 있습니다.<br>
또한 앱이 커질수록 Controller에 많은 코드가 쌓여 문제가 발생할 가능성이 높아집니다.<br>
그리고 특히 안드로이드에서는 액티비티 혹은 프래그먼트가 View와 Controller를 둘다 갖고 있기 때문에, 하나의 클래스에서 많은 로직을 처리하게 되는 문제가 발생하게 됩니다.<br>
그래서 일반적으로 안드로이드에서의 MVC패턴은 권장되지 않습니다.
<br>
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/1033d43e-25c1-4049-af61-401fca7bb800)
<br>
<br>

![image](https://github.com/sdhong0609/tech-interview-study/assets/78577085/e1077a0e-9310-4cf4-87fd-48d9f60c7167)

