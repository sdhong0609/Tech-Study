# Hilt 기본 요소 (Dagger와 동일)
### Component
Module에서 제공받은 의존성 객체를 조합하여 필요한 곳에 주입하는 역할을 합니다. Dagger는 Component를 매번 만들어야 하지만, Hilt는 이미 라이브러리에 만들어져 있기 때문에, 따로 Component를 만들어줄 필요 없이 표준화된 Component를 사용하면 됩니다.

### Module
Module은 의존성 객체들을 모아놓은 공간으로 Component에 의존성 객체를 제공하는 역할을 합니다.

### Provider (이것도 기본 요소인지는 아직 의문)
Provider 메서드는 Module 내에 정의되며, 해당 Module이 Component에 제공할 객체를 생성하고 제공하는 역할을 합니다.
(* 참고 : https://kotlinworld.tistory.com/63)
