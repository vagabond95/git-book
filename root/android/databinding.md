# Databinding

## observableField.set\(\) 메소드 호출 후, notify 가 안되는 이

observableField 의 set 메소드를 이용하여 데이터를 전달했음에도 불구하고 가끔 정상적으로 전달되지 않는 이슈가 있었음.

이유는 set 메소드 내부구에서 이전에 전달되었던 데이터와 **같은 경우** notify 를 호출하지 않음.  따라서  set  호출 이후에  명시적으로  notifyChange\(\)  를 호출해주면  정상적으로  전달됨 . 



