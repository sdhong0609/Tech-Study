# Event Wrapper 사용 이유
ViewModel에서 LiveData를 사용해서 이벤트를 처리하면 이벤트가 한번만 발생하는 것이 아니라, 이벤트가 중복되어 나타나는 문제가 발생합니다.<br>
예를 들어 화면 회전과 같은 환경 변화가 일어나게 되면 Activity는 파괴된 후 다시 생성되는데, ViewModel은 파괴되지 않고 그대로 살아있기 때문에 ViewModel 안의 데이터들은 그대로 유지됩니다.<br>
Activity가 다시 생성되고 ViewModel 안에 있는 LiveData를 다시 한번 observe하게 되면, 기존의 데이터가 적용되어 이벤트가 한 번 더 발생합니다.<br>
그래서 Event Wrapper라는 개념을 사용하여, 이벤트가 한 번만 발생하게 합니다. Event 클래스 내부에는 이벤트가 이미 발생하였는지를 판단하는 hasBeenHandled 변수가 포함되어 있습니다.
<br>
<br>

#### Event.kt
``` kotlin
import androidx.lifecycle.Observer

/**
 * Used as a wrapper for data that is exposed via a LiveData that represents an event.
 */
open class Event<out T>(private val content: T) {

    var hasBeenHandled = false
        private set // Allow external read but not write

    /**
     * Returns the content and prevents its use again.
     */
    fun getContentIfNotHandled(): T? {
        return if (hasBeenHandled) {
            null
        } else {
            hasBeenHandled = true
            content
        }
    }

    /**
     * Returns the content, even if it's already been handled.
     */
    fun peekContent(): T = content
}

class EventObserver<T>(private val onEventUnhandledContent: (T) -> Unit) : Observer<Event<T>> {
    override fun onChanged(event: Event<T>) {
        event.getContentIfNotHandled()?.let { value ->
            onEventUnhandledContent(value)
        }
    }
}
```
