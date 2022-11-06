## AppBar
<img src="https://user-images.githubusercontent.com/73378472/199906735-b796ed80-2fd0-4310-9892-755f4afd9123.png"/><br/>

```dart
AppBar(
  automaticallyImplyLeading: false,
  centerTitle: true,
  backgroundColor: Colors.transparent,
  systemOverlayStyle: SystemUiOverlayStyle.light,
  elevation: 0.0,
  leading: IconButton(
  icon: const Icon(
    Icons.arrow_back_sharp,
  ),
  onPressed: () {},
  ),
  actions: [
    IconButton(
      icon: const Icon(
        Icons.close,
      ),
      onPressed: () {},
    )
  ],
  titleSpacing: 0.0,
  title: const Text("title"),
),
```

> 스크린 상단에 들어가는 **AppBar**입니다.

> **title**옵션에 스크린 이름을 표시 할 수 있고 **leading**, **actions** 옵션으로 왼쪽, 오른쪽 위젯을 추가 할 수 있습니다.

> **automaticallyImplyLeading**을 true로 할 경우 자동으로 왼쪽에 뒤로가기 버튼이 활성화 됩니다. (leading옵션이 null이어야 합니다.)

- 문서: https://api.flutter.dev/flutter/material/AppBar-class.html


