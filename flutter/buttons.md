# Buttons
> In flutter,  button is disabled when `onPress` property is null. Therefore, you won't have any `disabled` property provided in button widgets.

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

## Elevated Button
<img src="https://user-images.githubusercontent.com/73378472/198944813-3fb5be74-97a2-4ddd-9f52-7bfdbc7dda44.png" width="200"/><br/>

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
> **Note:** The **MaterialButton** doesn't have shape property. `Flutter` recommends not to use this one and rather use `RaisedButton` or `FlatButton`.

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
> **Note:** The **RawMaterialButton** doesn't have `shape` property as well as `color`.  `FlatButton` and `RaisedButton` is superset of `RawMaterialButton`.

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

## IconButton
<img src="https://user-images.githubusercontent.com/73378472/198944816-1db29473-f267-4757-a2b9-a35997f9f722.png" width="200"/>

```dart
IconButton(onPressed: () {}, icon: const Icon(Icons.icecream)),
```

## FloatingActionButton
<img src="https://user-images.githubusercontent.com/73378472/198944815-b30a93f5-eb4c-4ec0-9c93-e8246db47478.png" width="200"/>

```dart
FloatingActionButton(
  onPressed: () {},
  backgroundColor: Colors.green,
  child: const Icon(Icons.navigation),
),
```

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
> **Note:** To map the **DropdownButton** with `keys` and `values` pair, you can use it like below.
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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU5MTU3NTQzLDIwMjExNDc3NywxMDM1MT
Y4LC0xNTMyMjc2MTU0LC0xODQyMDM2Mzk5LDEzMTc0NzYxMzEs
MjA2MjIxMTMwOCwxMTI5MTgxNjcxLDM4MTM4NzM0XX0=
-->