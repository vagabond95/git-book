# RecyclerView

## Focus 관리

RecyclerView 특성상 스크롤 후 더이상 화면에 보이지 않는 아이템은 일시적으로 제거된다. 이때 포커스를 가지고 있었다면 이를 해제시킨다. 따라서 EditText 와 궁합이 좋지 않으므로, EditText 가 ViewHolder 에 들어가는 특수한 케이스일 경우 ScrollView 로 구현하는 것을 고려해봐야한다.

