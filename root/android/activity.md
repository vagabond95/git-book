# Activity

## overridePendingTransition\(\)

Activity 의 Transition 에니메이션을 지정할 수 있음. super 메소드 다음에 호출해줘야 정상 작동

```java
super.onCreate(..)
overridePendingTransition(showAnim, hideAnim)

super.finish()
overridePendingTransition(showAnim, hideAnim)
```

