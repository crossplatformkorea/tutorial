# TabBar

## DefaultTabBar
<img src="https://user-images.githubusercontent.com/73378472/199385224-92788b74-9d0f-4b16-b59c-5f44ee6af024.gif"/>

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

## BottomNavigationBar
<img src="https://user-images.githubusercontent.com/73378472/199385030-d8dc980b-176e-4bc0-9abb-830f1bbb2373.gif"/>

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

> **Note:** Default BottomNavigationBar.

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

> **Note:** Example of setting _selectedIndex and _widgetOptions.

## Radius BottomNavigationBar
<img src="https://user-images.githubusercontent.com/73378472/199385033-17f0b0af-5763-4afe-9746-32c8c298dbd3.gif"/>

```dart
Scaffold(
  extendBody: true, // If true, the screen will be shown behind the BottomNavigationBar
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

> **Note:** If you use **Radius BottomNavigationBar**, it is natural to set the extendBody option to true.

## Collapsible TabBar
<img src="https://user-images.githubusercontent.com/73378472/199413457-ab9d0cb3-dac0-443d-9071-693d5723d9dd.gif"/>

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
      body: const Center(
        child: Text("Sample text"),
      ),
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

> **Note** When the **CollapsibleTabBar** is scrolled, the tab is pinned to the top