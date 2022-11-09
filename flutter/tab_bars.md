# TabBar

## DefaultTabBar
<img src="https://user-images.githubusercontent.com/73378472/199385224-92788b74-9d0f-4b16-b59c-5f44ee6af024.gif"/><br/>

```dart
DefaultTabController(
  initialIndex: 1,
  length: 3,
  child: Scaffold(
    appBar: AppBar(
      bottom: const PreferredSize(
        preferredSize: Size.fromHeight(55),
        child: SizedBox(
          height: 65,
          child: TabBar(
            padding: EdgeInsets.only(top: 10),
            indicatorPadding: EdgeInsets.all(0),
            labelPadding: EdgeInsets.all(0),
            unselectedLabelColor: Colors.black,
            labelColor: Color(0xffFF4B84),
            indicatorColor: Color(0xffFF4B84),
            tabs: <Widget>[
              Tab(icon: Icon(Icons.tag_faces), text: '메뉴1',),
              Tab(icon: Icon(Icons.add_circle_sharp), text: '메뉴2'),
              Tab(icon: Icon(Icons.info), text: '메뉴3'),
            ],
          ),
        ),
      ),
    ),
    body: TabBarView(children: <Widget>[
      // physics: NeverScrollableScrollPhysics(),
      Container(
        color: Colors.yellow,
      ),
      Container(
        color: Colors.orange,
      ),
      Container(
        color: Colors.red,
      ),
    ]),
  ),
);
```

상단탭 클릭으로 화면 이동을 할 수 있는 **DefaultTabBar**입니다 또한 화면내에서 좌우 스와이프로도 화면을 이동 할 수 있습니다.(`TabBarView`의 `physics` 옵션을 활용해 스와이프를 막을수도 있습니다)
PreferredSize옵션을 사용해 Tab의 높이를 조정 할 수도 있고, 선택된 탭과 안된 탭에 따로 스타일을 적용할 수도 있습니다.

- 문서: https://api.flutter.dev/flutter/material/TabBar-class.html

## BottomNavigationBar
<img src="https://user-images.githubusercontent.com/73378472/199385030-d8dc980b-176e-4bc0-9abb-830f1bbb2373.gif"/><br/>

```dart
Scaffold(
  body: Center(child: _widgetOptions.elementAt(_selectedIndex)),
  bottomNavigationBar: BottomNavigationBar(
    items: const <BottomNavigationBarItem>[
      BottomNavigationBarItem(
        icon: Icon(Icons.home),
        label: 'Home',
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.business),
        label: 'Business',
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.school),
        label: 'School',
      ),
    ],
      currentIndex: _selectedIndex,
      selectedItemColor: Colors.amber[800],
      onTap: (int index) {
        setState(() {
          _selectedIndex = index;
        },
      );
    },
  ),
);
```

하단탭 클릭으로 화면 이동을 할 수 있는 **BottomNavigationBar**입니다 **BottomNavigationBar**에 `BottomNavigationBarItem` 리스트가 있습니다, `currentIndex`을 설정하고 `onTap`옵션으로 클릭된 index를 할당하여 화면을 이동시킵니다.

- 문서: https://api.flutter.dev/flutter/material/BottomNavigationBar-class.html

```dart
int _selectedIndex = 0;
static const TextStyle optionStyle =
  TextStyle(fontSize: 30, fontWeight: FontWeight.bold);
static const List<Widget> _widgetOptions = <Widget>[
  Text(
    'Index 0: Home',
    style: optionStyle,
  ),
  Text(
    'Index 1: Business',
    style: optionStyle,
  ),
  Text(
    'Index 2: School',
    style: optionStyle,
  ),
];
```

3개의 **BottomNavigationBarItem** 리스트 예시입니다 리스트는 최소 2개이상 있어야합니다.

## Radius BottomNavigationBar
<img src="https://user-images.githubusercontent.com/73378472/199385033-17f0b0af-5763-4afe-9746-32c8c298dbd3.gif"/><br/>

```dart
Scaffold(
  extendBody: true,
  body: Center(child: _widgetOptions.elementAt(_selectedIndex)),
  bottomNavigationBar: Container(
    height: 100,
    decoration: const BoxDecoration(
      boxShadow: <BoxShadow>[
        BoxShadow(color: Color.fromRGBO(0, 0, 0, 0.2), blurRadius: 40),
      ],
    ),
      child: ClipRRect(
        borderRadius: const BorderRadius.only(
          topRight: Radius.circular(40),
          topLeft: Radius.circular(40),
        ),
        child: BottomNavigationBar(
        // backgroundColor: Colors.blueAccent,
        elevation: 1,
        items: <BottomNavigationBarItem>[
          BottomNavigationBarItem(
            icon: _selectedIndex == 0
              ? const Icon(Icons.home_filled)
              : const Icon(Icons.home_outlined),
              label: 'Home',
          ),
          BottomNavigationBarItem(
            icon: _selectedIndex == 1
              ? const Icon(Icons.chat)
              : const Icon(Icons.chat_outlined),
            label: 'Chat',
          ),
          BottomNavigationBarItem(
            icon: _selectedIndex == 2
              ? const Icon(Icons.school)
              : const Icon(Icons.school_outlined),
            label: 'School',
          ),
        ],
        currentIndex: _selectedIndex,
        selectedItemColor: const Color(0xffFF4B84),
        unselectedFontSize: 14,
        selectedFontSize: 14,
        onTap: (int index) {
          setState(
            () {
                _selectedIndex = index;
            },
          );
        },
      ),
    ),
  ),
);
```

**BottomNavigationBar**에 [ClipRRect][ClipRRectlink] 위젯을 활용해 좌우 radius 곡선을 준 navigation입니다. 이 경우 `Scaffold`에 `extendBody: true`을 주어야 자연스러운 ui를 구성할 수 있습니다.

[ClipRRectlink]: https://api.flutter.dev/flutter/widgets/ClipRRect-class.html 

<img src="https://user-images.githubusercontent.com/73378472/199655497-a9c317b0-3a83-4bec-ae2f-c1b3fb900f5a.gif"/><br/>
> **extendBody: false** 화면이 아래로 스크롤 될때, navigation 배경에 가려집니다.

<img src="https://user-images.githubusercontent.com/73378472/199655502-390d4b08-985f-4805-b132-3ecd941895ad.gif"/><br/>
> **extendBody: true** 화면이 아래로 스크롤 될때, navigation 배경에 가려지지 않습니다.

## Collapsible TabBar
<img src="https://user-images.githubusercontent.com/73378472/199413457-ab9d0cb3-dac0-443d-9071-693d5723d9dd.gif"/><br/>

```dart
Scaffold(
  body: DefaultTabController(
    initialIndex: 1,
    length: 3,
    child: NestedScrollView(
      headerSliverBuilder: (BuildContext context, bool innerBoxIsScrolled) {
        return <Widget>[
          const SliverAppBar(
            backgroundColor: Color(0xffFF4B84),
            expandedHeight: 200.0,
            floating: false,
            pinned: true,
            flexibleSpace: FlexibleSpaceBar(
              centerTitle: true,
              title: Text(
                "Collapsing Toolbar",
                style: TextStyle(
                  color: Colors.white,
                  fontSize: 16.0,
                ),
              ),
            ),
          ),
          SliverPersistentHeader(
            delegate: _SliverAppBarDelegate(
              const TabBar(
                labelColor: Colors.black87,
                unselectedLabelColor: Colors.grey,
                tabs: [
                  Tab(icon: Icon(Icons.info), text: "Tab 1"),
                  Tab(icon: Icon(Icons.lightbulb_outline), text: "Tab 2"),
                  Tab(icon: Icon(Icons.backpack), text: "Tab 3"),
                ],
              ),
            ),
          pinned: true,
          ),  
        ];
      },
      body: TabBarView(children: <Widget>[
        Container(
          color: Colors.yellow,
        ),
        Container(
          color: Colors.orange,
        ),
        Container(
          color: Colors.red,
        ),
      ]),
    ),
  ),
);

class _SliverAppBarDelegate extends SliverPersistentHeaderDelegate {
  _SliverAppBarDelegate(this._tabBar);

  final TabBar _tabBar;

  @override
  double get minExtent => _tabBar.preferredSize.height;
  @override
  double get maxExtent => _tabBar.preferredSize.height;

  @override
  Widget build(
      BuildContext context, double shrinkOffset, bool overlapsContent) {
    return Container(
      child: _tabBar,
    );
  }

  @override
  bool shouldRebuild(_SliverAppBarDelegate oldDelegate) {
    return false;
  }
}
```
[SliverAppBar][SliverAppBarlink] 위젯을 활용하여 스크롤 가능한 `TabBar`입니다 `pinned: true` 옵션으로 상단에 TabBar가 충돌했을때 고정됩니다. [FlexibleSpaceBar][FlexibleSpaceBarlink]로 상단에 표시될 화면을 제공하고 [SliverPersistentHeader][SliverPersistentHeaderlink] 옵션으로 Tab내용을 구성합니다
delegate 옵션 SliverPersistentHeaderDelegate에 props로 TabBar를 주는 방식으로 구성됩니다.

[SliverAppBarlink]: https://api.flutter.dev/flutter/material/SliverAppBar-class.html 
[FlexibleSpaceBarlink]: https://api.flutter.dev/flutter/material/FlexibleSpaceBar-class.html
[SliverPersistentHeaderlink]: https://api.flutter.dev/flutter/widgets/SliverPersistentHeader-class.html
[SliverPersistentHeaderDelegatelink]: https://api.flutter.dev/flutter/widgets/SliverPersistentHeaderDelegate-class.html
