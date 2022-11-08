# Buttons
> 플러터에서 버튼은 disabled 속성이 true일때 `onPress`속성은 null 이됩니다. 그러므로 버튼 위젯에는 disabled 속성이 제공되지 않습니다.

## Text Button
<img src="https://user-images.githubusercontent.com/73378472/198944827-9262098e-a21d-4aca-93e6-393d048ee00c.png" width="200"/><br/>

```dart
TextButton(
  onPressed: () {},
  child: const Text(
    'TextButton',
    style: TextStyle(
      color: Colors.black,
      fontSize: 16.0,
    ),
  ),
),
```
[TextButton][TextButtonLink]은 Text에 `onPressed` 속성으로 클릭 효과를 줄 수 있습니다. 높이가 없고 단순한 평면 버튼입니다.

[TextButtonLink]:https://api.flutter.dev/flutter/material/TextField-class.html

## Elevated Button
<img src="https://user-images.githubusercontent.com/73378472/199157231-2c8b784f-8e65-41bf-bf67-b5a09d84fd9b.gif"/><br/>

```dart
ElevatedButton(
  style: ButtonStyle(
    padding: MaterialStateProperty.all(const EdgeInsets.symmetric(
      horizontal: 16.0,
      vertical: 12.0,
    )),
    shape: MaterialStateProperty.all<RoundedRectangleBorder>(
      RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(10.0),
        side: const BorderSide(color: Colors.red),
      ),
    ),
  ),
  onPressed: () {},
  child: const Text(
    'ElevatedButton',
    style: TextStyle(
    color: Colors.white,
    fontSize: 16.0,
    ),
  ),
),
```

[ElevatedButton][ElevatedButtonLink]은 버튼을 누를 때 Material.elevation(높이)가 증가 하는 Material 위젯 에 표시되는 하위 레이블 입니다 또한 잉크가 증가하는 듯한 효과가 있습니다.
[dialogs][dialogLink] or [cards][cardLink]같은 이미 높은 위젯 위에 사용하면 안됩니다.

[ElevatedButtonLink]:https://api.flutter.dev/flutter/material/ElevatedButton-class.html
[dialogLink]:https://api.flutter.dev/flutter/material/Dialog-class.html
[cardLink]:https://api.flutter.dev/flutter/material/Card-class.html

## OutlinedButton
<img src="https://user-images.githubusercontent.com/73378472/198944821-afa6e752-95a9-4ce6-934d-0f7f9376a297.png" width="200"/><br/>

```dart
OutlinedButton(
  onPressed: () {},
  child: const Text(
    'OutlinedButton',
  style: TextStyle(color: Colors.black, fontSize: 16),
)),
```

[OutlinedButton][OutlinedButtonLink] 는 기본 테두리 윤곽선이 있고 높이가 없는 TextButton 입니다.

[OutlinedButtonLink]:https://api.flutter.dev/flutter/material/OutlinedButton-class.html
## MaterialButton
<img src="https://user-images.githubusercontent.com/73378472/198944820-51b5a714-6524-41c4-a96c-b8575d556694.png" width="200"/><br/>

```dart
MaterialButton(  
  padding: EdgeInsets.symmetric(
    horizontal: 16.0, vertical: 12.0,
  ),
  color: Colors.red,  
  onPressed: () { },  
  child: Text(  
    'MaterialButton',
    style: TextStyle(  
    color: Colors.white,  
    fontSize: 16.0,  
  ),
),
```
[MaterialButton][MaterialButtonLink] 은 shape 속성이 없습니다 이 버튼은 곧 `deprecated` 됩니다 대신 `ElevatedButton` 또는 `TextButton`를 사용하세요.

[MaterialButtonLink]:https://api.flutter.dev/flutter/material/MaterialButton-class.html
## RawMaterialButton
<img src="https://user-images.githubusercontent.com/73378472/198944825-bfb29ac0-9358-4ef8-8eab-b31a04c319ba.png" width="200"/><br/>

```dart
RawMaterialButton(  
  padding: EdgeInsets.symmetric(
    horizontal: 16.0, vertical: 12.0,
  ),
  color: Theme.Colors.foodieon,  
  onPressed: () { },  
  child: Text(  
    'RawMaterialButton',
    style: TextStyle(  
    color: Colors.white,  
    fontSize: 16.0,  
  ),
),
```
[RawMaterialButton][RawMaterialButtonLink]은 `shape`, `color` 속성이 없습니다 테마 기본값을 상속받지 않습니다. 이 버튼 역시 곧 `deprecated` 됩니다 `ElevatedButton` 또는 `TextButton`를 사용하세요.

[RawMaterialButtonLink]:https://api.flutter.dev/flutter/material/RawMaterialButton-class.html

## ToggleButtons
<img src="https://user-images.githubusercontent.com/73378472/198955932-21b6c4c5-c3bb-4aac-99a1-2ef6b6448f5a.gif"/>

```dart
ToggleButtons(
  isSelected: const <bool>[false, false, false],
  onPressed: (_) {},
  children: const [
    Padding(
      padding: EdgeInsets.symmetric(horizontal: 16.0),
      child: Text('BUTTON 1'),
    ),
    Padding(
      padding: EdgeInsets.symmetric(horizontal: 16.0),
      child: Text('BUTTON 2'),
    ),
    Padding(
      padding: EdgeInsets.symmetric(horizontal: 16.0),
      child: Text('BUTTON 3'),
    ),
  ],
),
```
[ToggleButtons][ToggleButtonsLink]은 여러개의 옵션을 선택할 수 있는 버튼입니다. `isSelected` 속성에 bool타입으로 선택 됐는지 여부를 체크할 수 있으며 `isSelected`에 제공된 배열의 길이와 `children` 속성 길이는 같아야 합니다.

[ToggleButtonsLink]:https://api.flutter.dev/flutter/material/ToggleButtons-class.html

## IconButton
<img src="https://user-images.githubusercontent.com/73378472/198944816-1db29473-f267-4757-a2b9-a35997f9f722.png" width="200"/>

```dart
IconButton(onPressed: () {}, icon: const Icon(Icons.icecream)),
```

[IconButton][IconButtonLink]은 아이콘에 버튼 onPressed 속성을 줄 수 있습니다 상위 항목 중 하나가 [Material][MaterialLink] 위젯이어야 합니다.

[IconButtonLink]:https://api.flutter.dev/flutter/material/IconButton-class.html
[MaterialLink]:https://api.flutter.dev/flutter/material/Material-class.html

## FloatingActionButton
<img src="https://user-images.githubusercontent.com/73378472/198944815-b30a93f5-eb4c-4ec0-9c93-e8246db47478.png" width="200"/>

```dart
FloatingActionButton(
  onPressed: () {},
  backgroundColor: Colors.green,
  child: const Icon(Icons.navigation),
),
```

[FloatingActionButton][FloatingActionButtonLink]은 화면에 위치가 고정되어 떠 있는 고정 버튼입니다.
화면당 최대 하나의 버튼을 사용하고 "만들기", "공유" 또는 "탐색"과 같은 긍정적인 작업에 사용해야 합니다.

[FloatingActionButtonLink]:https://api.flutter.dev/flutter/material/FloatingActionButton-class.html

## PopupMenuButton
<img src="https://user-images.githubusercontent.com/73378472/198944823-ae6530f2-6f7e-45b8-ba1b-7dab49d7fffc.gif"/>

```dart
PopupMenuButton<String>(
  onSelected: (_) {},
  itemBuilder: (BuildContext context) => <PopupMenuEntry<String>>[
    const PopupMenuItem<String>(
      value: "itemOne",
      child: Text('Item 1'),
    ),
    const PopupMenuItem<String>(
      value: "itemTwo",
      child: Text('Item 2'),
    ),
    const PopupMenuItem<String>(
      value: "itemThree",
      child: Text('Item 3'),
    ),
    const PopupMenuItem<String>(
      value: "itemFour",
      child: Text('Item 4'),
    ),
  ],
),
```

[PopupMenuButton][PopupMenuButtonLink]은 여러개의 옵션을 선택 할 수 있는 버튼이고 열고 닫을 수 있습니다
누를 때 메뉴를 표시하고 항목이 선택되어 메뉴가 닫히면 `onSelected` 를 호출합니다. `onSelected` 에 전달된 값은 선택한 메뉴 항목의 값입니다.

[PopupMenuButtonLink]:https://api.flutter.dev/flutter/material/PopupMenuButton-class.html

## DropDownButtons
<img src="https://user-images.githubusercontent.com/73378472/198944810-ee9d6cc4-42f0-48e0-97f9-a9e8c1b0b7f7.gif"/><br/>

```dart
Column(  
  children: <Widget>[  
    DropdownButton<String>(  
      items: <String>[  
        'KEY1', 'KEY2', 'KEY3', 'KEY4',
      ].map((String str) {
        return new DropdownMenuItem<String>(  
          value: str,  
          child: new Text(str),  
        );
      }).toList(),  
      onChanged: (_) {},  
    ),
  ],
),
```
[DropdownButton][DropdownButtonLink]을 사용하면 사용자가 여러 항목 중에서 선택할 수 있습니다. 버튼은 현재 선택된 항목과 다른 항목을 선택하기 위한 메뉴를 여는 화살표를 보여줍니다. 
`key`, `values`를 맵핑해서 아래처럼 사용 할 수 있습니다.

[DropdownButtonLink]:https://api.flutter.dev/flutter/material/DropdownButton-class.html

```dart
Column(  
  children: <Widget>[  
    DropdownButton<Map>(  
      items: <Map<String, String>>[  
       { 'key': 'KEY1', 'value': 'VALUE1' },  
       { 'key': 'KEY2', 'value': 'VALUE2' },  
       { 'key': 'KEY3', 'value': 'VALUE3' },  
       { 'key': 'KEY4', 'value': 'VALUE4' },  
       { 'key': 'KEY5', 'value': 'VALUE5' },  
     ].map((Map<String, String> value) {  
        return new DropdownMenuItem<Map<String, String>>(  
          value: value,  
          child: new Text(value['value']),  
        );
      }).toList(),  
      onChanged: (_) {},  
    ),
  ],
),
```