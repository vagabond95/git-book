# TextView

## Link 속성을 걸어줄 때는 autoLink 를 활용하자.

TextView 에서 Link 속성을 걸어줄 때는 2가지 방법을 이용할 수 있음

1. Linkify.addLink\(\) 를 이용하여 추가
2. TextView.setAutoLinkMask\(\) / 혹은 android:autoLink 속성

그런데 Linkify 를 이용해서 속성을 걸어줄 경우 아래와 같은 케이스에서는 포맷이 적용 안됨.

```text
Linkify.addLink(textView, Linkfy.WEB_URL)
textView.setText("http://naver.com")
```

왜냐하면 setText 과정에서 설정된 setAutoLinkMask 값을 기준으로 span 을 먹이는데, Linkify.addLink 는 스타일만 적용할 뿐 setAutoLinkMask  값과는 연관이 없음. 따라서 setAutoLinkMask 값이 없어서 이전에 걸어놨던 link span style 이 다시 리셋되어 일반 텍스트 포맷으로 보이게 됨.

따라서 웬만하면 autoLink 를 이용하자. 어차피 내부에서 Linkify.addLink 를 이용하는 것은 똑같음.

## movementMethod 를 활용하여 Linkable 텍스트 클릭시 이벤트를 핸들링 할 수 있음.

