# Hilt 어노테이션
첫번째로 @HiltAndroidApp은, 앱의 Application 클래스에 지정하여 Hilt를 초기화합니다. Hilt가 앱의 컴포넌트 계층 구조를 구성하고 DI를 가능하게 해줍니다.<br>

두번째로 @AndroidEntryPoint는 액티비티, 프래그먼트 등 안드로이드 클래스에 지정하여, Hilt가 해당 클래스에 의존성을 주입할 수 있게 합니다.<br>

세번째로 @HiltViewModel은 ViewModel 클래스에 지정하여, ViewModel을 의존성 주입 가능한 객체로 인식하게 만듭니다.<br>

네번째로 @Inject는 주입할 필드, 생성자 또는 메서드에 지정됩니다. 해당 필드나 생성자에 대한 인스턴스를 자동으로 생성하고 주입 가능하게 합니다.<br>

다섯번째로 @Module은 모듈 클래스에 지정됩니다. 해당 모듈은 주입할 의존성을 제공하는 방법을 정의합니다.<br>

여섯번째로 @Provides는 모듈 내의 메서드에 지정됩니다. 해당 메서드는 의존성을 제공하고 Hilt에 의해 주입될 수 있습니다.<br>

마지막으로 @InstallIn은 모듈 클래스에 지정되며, 모듈을 특정 컴포넌트에 설치하는 데 사용됩니다. @SingletonComponent, @ActivityRetainedComponent, @ActivityComponent 등과 같은 Hilt 컴포넌트를 대상으로 합니다.
