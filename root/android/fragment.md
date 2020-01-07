# Fragment

## FragmentTransaction - setCustomAnimations\(\)

1. fragment 가 add 혹은 replace 될 때 animation 을 설정할 수 있음.
2. transaction 흐름 내에서  setCustomAnimations 호출을 add, replace 보다 뒤에서 할 경우 animation 이 적용되지 않음
3. addToBackStack\(\) 으로 fragment 를 backStack 에 넣는 경우와 넣지 않는 경우 사용되는 메소가 다름

```java
setCustomAnimations(int i1, int i2) // addToBackStack X
setCustomAnimations(int i1, int i2, int i3, int i4) // addToBackStack O
```



## FragmentTransaction - `commitAllowingStateLoss()`

일반적으로 activity 의 onSaveInstance\(\) 가 호출된 이후 commit 을 호출 할 경우 exception 발생함.

해당 메소드를 쓰면 activity 의 onSaveInstance 호출 이후 해당 메소드가 불려도, exception 이 throw 되지 않고 transaction 내용이 commit 됨. 다만, saveInstance 에 저장되지 않을 수 있는 점을 인지하고 사용 할 것 

ref : [https://medium.com/inloopx/demystifying-androids-commitallowingstateloss-cb9011a544cc](https://medium.com/inloopx/demystifying-androids-commitallowingstateloss-cb9011a544cc)

