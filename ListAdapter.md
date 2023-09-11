# ListAdapter

### ListAdapter를 사용하는 이유
리사이클러뷰의 데이터가 변하면 리사이클러뷰 어댑터가 제공하는 notifyItem 메서드를 호출하거나, notifyDataSetChanged() 메서드를 호출해서, 데이터 집합이 변경되었음을 알릴 수 있습니다.<br>
하지만 데이터가 변경되는 방식을 확인해서 일일이 notify를 해주는 것은 번거롭기도 하고, 갱신이 필요없는 ViewHolder를 같이 갱신하는 불필요한 작업이 생길 수도 있습니다.<br>
그래서 이러한 번거로운 작업을 피하고, 변경해야 하는 아이템들만 효율적으로 변경해주기 위해서 ListAdapter를 사용합니다.

### DiffUtil
ListAdapter의 기원이 되는 클래스 중 DiffUtil 클래스가 있는데, 두 데이터 셋을 받아서 그 차이를 계산해주는 클래스입니다.<br>
areItemsTheSame으로 비교대상인 두 아이템이 같은 객체인지 확인하고, areContentsTheSame으로 두 아이템이 같은 데이터를 가지는지 확인합니다.

### AsyncListDiffer
하지만 DiffUtil 클래스는 아이템의 개수가 많은 경우 비교연산하는 시간이 길어지기 때문에, 개발자가 직접 백그라운드 스레드에서 처리해야 합니다. (UI 스레드에서 처리하면 길어진 시간 때문에 UI에 문제가 발생할 수 있기 때문!!)<br>
이러한 작업을 편하게 하기 위해 AsyncListDiffer라는 클래스가 나왔고, 내부적으로 비교연산을 백그라운드 스레드에서 처리하기 때문에 개발자는 스레드를 신경쓰지 않아도 됩니다.<br>

### ListAdapter
ListAdapter는 AsyncListDiffer를 더 편하게 사용하도록 랩핑한 클래스로, 리사이클러뷰 어댑터를 만들 때 ListAdatper를 상속하면 됩니다.<br>
ListAdapter로 구현하면 데이터가 어떻게 바뀌든 간에 submitList() 로 전체 리스트를 넘겨주기만 하면, 어댑터가 자동으로 백그라운드 스레드에서, 이전 데이터와 새로운 데이터의 차이를 계산하여 화면을 갱신해줍니다.<br>
이를 통해 RecyclerView의 업데이트와 화면 갱신이 효율적으로 이루어집니다.<br>
