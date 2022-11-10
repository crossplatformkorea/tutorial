# Views

## List View
<img src="https://user-images.githubusercontent.com/73378472/200172490-cb064da6-7bd8-42c1-bc74-815292db57e0.gif"/></br>

```dart
ListView(
  scrollDirection: Axis.vertical,
  reverse: true,
  addAutomaticKeepAlives: false,
  cacheExtent: 100.0,
  // physics: NeverScrollableScrollPhysics(),
  children: [],
)
```
화면을 스크롤되게 하고 view를 컨트롤 할 수 있게 해주는 [ListView][ListViewLink]입니다.
`scrollDirection` 속성으로 가로로 스크롤 되게 할 수 있고, `reverse` 속성으로 반대로 리스트를 보여 줄 수 있습니다.
[addAutomaticKeepAlives][KeepAliveLink] 속성이 false일 경우 화면 밖 리스트 렌더가 유지되지 않게 해줄 수 있습니다.
또한, [cacheExtent][cacheExtentLink] 속성이 100일 경우 100픽셀 만큼 화면 밖에서 아이템들을 미리 빌드를 해주기 때문에 listView 로딩을 기다리지 않아도 됩니다.
physics: `NeverScrollableScrollPhysics()`은 스크롤이 안되게 하는 속성입니다.

[KeepAliveLink]:https://api.flutter.dev/flutter/widgets/KeepAlive-class.html
[cacheExtentLink]:https://api.flutter.dev/flutter/widgets/ScrollView/cacheExtent.html
[ListViewLink]:https://api.flutter.dev/flutter/widgets/ListView-class.html

```dart
ListView.separated(
  scrollDirection: Axis.vertical,
  itemBuilder: (_, index) => Text("text $index"),
  separatorBuilder: (a, b) => Divider(),
  itemCount: 20),
)
```

**ListView.separated**은 list를 만들어서 동적으로 사용할 수 있게 해줍니다. `itemCount`에 갯수를 넣고, `itemBuilder`에 view를 넣어주면 됩니다.

## Grid View
<img src="https://user-images.githubusercontent.com/73378472/200179707-04a6eec1-be62-419e-bf3d-c1a45a80c04a.gif"/></br>

```dart
GridView.count(
  primary: false,
  padding: const EdgeInsets.all(20),
  crossAxisSpacing: 10,
  mainAxisSpacing: 10,
  crossAxisCount: 2,
  children: <Widget>[
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[100],
      child: const Text("1"),
    ),
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[200],
      child: const Text('2'),
    ),
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[300],
      child: const Text('3'),
    ),
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[400],
      child: const Text('4'),
    ),
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[500],
      child: const Text('5'),
    ),
    Container(
      padding: const EdgeInsets.all(8),
      color: Colors.teal[600],
      child: const Text('6'),
    ),
  ],
),
```

[GridView][GridViewLink] grid형태의 `ListView`입니다. `crossAxisCount`속성으로 열의 갯수를 정할 수 있고, `crossAxisSpacing`, `mainAxisSpacing`속성으로 view사이 간격을 줄 수 있습니다.
`primary` 속성이 true이면 실제로 스크롤 하기에 충분한 콘텐츠가 없는 경우에도 스크롤 뷰를 스크롤 할 수 있습니다. 

[GridViewLink]:https://api.flutter.dev/flutter/widgets/GridView-class.html