# Style

## TextView 에 밑줄 넣기

```text
spannableStringBuilder.setSpan(
    new UnderlineSpan(), 
    0, 
    end, 
    Spannable.SPAN_EXCLUSIVE_EXCLUSIVE
);
```

 &lt;u&gt;&lt;/u&gt; 태그 넣는 방법은 html escape 과정이 필요하므로 권장하지 않음.

