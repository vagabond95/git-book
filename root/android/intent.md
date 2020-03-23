# Intent

## 통화 다이얼화면까지 이동하 Intent

```text
// phoneUri 포맷 - tel:XXXXXXXXX
Intent intent = new Intent(Intent.ACTION_DIAL, Uri.parse(phoneUri));
mContext.startActivity(intent);
```

