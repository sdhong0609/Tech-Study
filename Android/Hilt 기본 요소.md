# Hilt 기본 요소
### Component
Component는 외부에서 주입할 의존성 클래스의 인스턴스를 생성하는 공간입니다. Module에서 제공받은 의존성 객체를 조합하여 필요한 곳에 주입하는 역할을 합니다. Dagger는 Component를 매번 만들어야 하지만, Hilt는 이미 라이브러리에 만들어져 있기 때문에, 따로 Component를 만들어줄 필요 없이 표준화된 Component를 사용하면 됩니다.

### Module
Module은 의존성 클래스의 인스턴스들을 모아놓은 공간으로 Component에 의존성 객체를 제공하는 역할을 합니다.
