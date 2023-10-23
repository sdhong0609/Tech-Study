# Hilt 기본 요소 (Dagger와 동일)
### Component
Module에서 제공받은 의존성 객체를 조합하여 필요한 곳에 주입하는 역할을 합니다.

### Module
Module은 의존성 객체들을 모아놓은 공간으로 Component에 의존성 객체를 제공하는 역할을 합니다.

### Provider (이것도 기본 요소인지는 아직 의문)
Provider 메서드는 Module 내에 정의되며, 해당 Module이 Component에 제공할 객체를 생성하고 제공하는 역할을 합니다.<br>
(* 참고 : https://kotlinworld.tistory.com/63)

<br>

# Hilt를 사용하는 이유 (Hilt의 장점)
첫번째로 다른 라이브러리에 비해 의존성 주입을 위한 코드 작성이 쉽고 난이도가 낮기 때문입니다. 대거는 Component를 매번 만들어야 하지만, Hilt는 이미 라이브러리에 만들어져 있기 때문에, 따로 Component를 만들어줄 필요 없이 표준화된 Component를 사용하면 됩니다. 개발자는 Module만 생성하고 @InstallIn 어노테이션으로 Compoent에 Module을 제공만 해주면 됩니다. 그래서 의존성 주입을 위한 코드가 간결해지고 가독성이 향상됩니다.<br>

두번째로 이미 만들어져 있는 Component들이 Activity, Fragment, ViewModel 등 안드로이드 클래스에 최적화되어 있기 때문입니다. Hilt는 생성된 Component 인스턴스를, 해당 안드로이드 클래스의 생명주기에 따라 자동으로 생성하고 파괴합니다. 그래서 Component 인스턴스의 생명주기를 관리할 필요성이 없어지고 메모리 누수도 발생하지 않습니다.<br>

세번째로 런타임이 아닌 컴파일 타임에 에러를 검출하기 때문에, 런타임 오류가 줄어들고 앱의 안정성을 향상시킵니다.<br>

마지막으로 현재 가장 많이 사용되는 안드로이드 의존성 주입 라이브러리라서, 정보를 검색하기도 쉬웠고 관련 코드도 찾기 쉬워서 사용했습니다.

