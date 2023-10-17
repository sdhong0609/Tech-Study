# Serializable vs Parcelable
Serializable과 Parcelable은 직렬화 및 역직렬화를 위해 사용하는 인터페이스로, Serializable은 자바에서 제공하는 인터페이스이고, Parcelable은 안드로이드에서 제공하는 인터페이스입니다.<br><br>
이 둘의 차이점은,<br>
첫번째로 속도 측면에서 Parcelable이 Serializable보다 빠릅니다. Serializable은 자바의 리플랙션을 사용하기 때문에 속도가 느리지만, Parcelable은 안드로이드 OS에서 직접 처리하기 때문에 속도가 빠릅니다.<br><br>
두번째로 메모리 사용 측면에서 봤을 때, Serializable은 자바 직렬화 메커니즘을 사용하는 반면, Parcelable은 안드로이드 메커니즘을 사용하기 때문에 메모리 사용량을 줄일 수 있습니다.<br><br>
세번째로 명시성 측면입니다. Serializable은 특별한 메서드 없이 직렬화되지만, Parcelable은 직렬화와 역직렬화 과정을 명시적으로 작성해야 하는 불편함이 있습니다. 이러한 불편함을 해결하려면 Parcelable을 자동으로 구현해주는 Parcelize 플러그인를 사용하면 됩니다.<br><br>
보통 객체 크기가 크거나 다른 플랫폼과도 호환해야 하는 경우 Serializable을 사용하고, 객체 크기가 작고 안드로이드 OS에서만 사용하는 경우 Parcelable을 사용합니다.<br>

(* 참고 : 자바의 리플렉션은 구체적인 클래스 타입을 알지 못하더라도 그 클래스의 메서드, 타입, 변수들에 접근할 수 있도록 해주는 자바 API를 말하며, 컴파일 시간이 아닌 실행 시간에 동적으로 특정 클래스의 정보를 추출할 수 있는 프로그래밍 기법입니다.)
