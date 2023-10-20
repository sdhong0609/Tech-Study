# Dagger, Hilt 기본 요소
### Component
Component는 외부에서 주입할 의존성 클래스의 인스턴스를 생성하는 공간입니다. Module에서 제공받은 의존성 객체를 조합하여 필요한 곳에 주입하는 역할을 합니다.

### Module
Module은 의존성 클래스의 인스턴스들을 모아놓은 공간으로 Component에 의존성 객체를 제공하는 역할을 합니다.

### Provider(Provides)
Provider는 인스턴스를 제공하는 역할을 합니다.
