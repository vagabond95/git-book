# Databinding

## observableField.set\(\) 메소드 호출 후, notify 가 안되는 이슈

observableField 의 set 메소드를 이용하여 데이터를 전달했음에도 불구하고 가끔 정상적으로 전달되지 않는 이슈가 있었음.

이유는 set 메소드 내부구에서 이전에 전달되었던 데이터와 **같은 경우** notify 를 호출하지 않음.  따라서  set  호출 이후에  명시적으로  notifyChange\(\)  를 호출해주면  정상적으로  전달됨 . 

```text
observableField.set(data);
observableField.notifyChange();
```

## executePendingBindings\(\)

강제로 바인딩되어있는 데이터들을 이용하여 View 를 갱신한다. 보통 recyclerView 에서 많이 사용함. 결국 UI thread 에 view set 테스트가 쌓이는 것이므로 너무 많이 호출돼면 퍼포먼스 이슈 생길 수 있음.

## bindingAdapter 와 콜백

1. 메소드 시그니쳐를 그대로 맞춰서 전달.

```text
@{viewModel::onChange}
```

2. 해당 콜백의 구현체를 넘겨줌

```text
@{Listener}
```

3. 람다식 이용

```text
@{param -> viewModel.onChange(param)}
```

이때 인자는 1개만 가능하다.

## custom BindingAdapter 만들시 주의사항

* BindinAdapter 메소드의 첫번째 인자는 항상 View 타입이어야 한다.



## &lt;merge&gt;

레이아웃 최상위 레벨에서 &lt;merge&gt; 를 사용하고 데이터바인딩 적용시 inflate 과정에서 에러. 개발자 가이드에서도 사용하지 말라고 나와있음. 이유는 좀 더 찾아볼 것 

## &lt;include&gt;

```text
<OuterView>

    <include/>

</OuterView>
```

이러한 구조의 View 가 있을 때 Outer depth 에서 include 의 View 에 정의된 데이터를 넘겨주고 싶을 경우 `bind:` 활용할 것

이때 bind 에 들어가는 이름은 반드시 include 에서 지정한 variable name 과 일치해야함.

