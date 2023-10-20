# Hilt 어노테이션
첫번째로 @HiltAndroidApp은, 앱의 Application 클래스에 이 어노테이션을 지정하여 Hilt를 초기화합니다. Hilt가 앱의 컴포넌트 계층 구조를 구성하고 DI를 가능하게 합니다.<br>

두번째로 @AndroidEntryPoint는 Android Framework 클래스들인 Activity, Fragment, Service, BroadcastReceiver 등에 이 어노테이션을 지정하여 Hilt가 해당 클래스의 종속성을 주입할 수 있도록 합니다.<br>

세번째로 @HiltViewModel은 ViewModel을 주입 가능한 객체로 인식하고 필요한 의존성을 주입할 수 있게 해줍니다.<br>

네번째로 @Inject는 주입할 필드, 생성자 또는 메서드에 지정됩니다. Hilt는 해당 필드나 생성자에 대한 인스턴스를 자동으로 생성하고 주입합니다.<br>

다섯번째로 @Module은 Hilt 모듈을 정의하는 클래스에 지정됩니다. 모듈은 주입할 종속성을 제공하는 방법을 정의합니다.<br>

여섯번째로 @Provides는 모듈 내의 메서드에 지정됩니다. 해당 메서드는 종속성을 제공하고 Hilt에 의해 주입될 수 있도록 합니다.<br>

마지막으로 @InstallIn은 모듈을 특정 컴포넌트에 설치하는 데 사용됩니다. @InstallIn 어노테이션은 모듈 클래스 위에 지정되며, @SingletonComponent, @ActivityRetainedComponent, @ActivityComponent 등과 같은 Hilt 컴포넌트를 대상으로 합니다.
