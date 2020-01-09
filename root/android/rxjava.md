# RxJava

## PublishSubject 와 onError

publishSubject 를 구독하는 subscriber 에서  onError 가  호출될 경우, publishSubject 는 해당 subscriber 와의  구독을 끊어버림. 이런상황을 맞이하면 디버깅하기 매우빡셈.

이를 대응하고자, onErrorResume / onErrorNext 같은 메소드를 통해 error 를 후킹하여 다시 emit 해줄 경우 구독해제 없이 정상적으로 작동.

