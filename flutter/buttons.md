# Buttons
> In flutter,  button is disabled when `onPress` property is null. Therefore, you won't have any `disabled` property provided in button widgets.

## Flat Button
<img src="https://firebasestorage.googleapis.com/v0/b/flutterdart-5d354.appspot.com/o/docs%2FFlatButton.gif?alt=media&token=8247fb6c-e9e8-46a4-90d6-13150c2c8cea"/><br/>
```dart
FlatButton(  
  padding: EdgeInsets.symmetric(
    horizontal: 16.0, vertical: 12.0,
  ),
  color: Colors.red,  
  shape: RoundedRectangleBorder(  
    borderRadius: BorderRadius.circular(10.0),  
  ),
  onPressed: () { },  
  child: Text(  
    'FlatButton',
    style: TextStyle(  
    color: Colors.white,  
    fontSize: 16.0,  
  ),
),
```

## Raised Button
<img src="https://firebasestorage.googleapis.com/v0/b/flutterdart-5d354.appspot.com/o/docs%2FRaisedButton.gif?alt=media&token=d849900e-7ebe-44d3-88b5-de18593afc34"/><br/>
```dart
RaisedButton(  
  padding: EdgeInsets.symmetric(
    horizontal: 16.0, vertical: 12.0,
  ),
  color: Colors.red,  
  shape: RoundedRectangleBorder(  
    borderRadius: BorderRadius.circular(10.0),  
  ),
  onPressed: () { },  
  child: Text(  
    'RaisedButton',
    style: TextStyle(  
    color: Colors.white,  
    fontSize: 16.0,  
  ),
),
```

## MaterialButton
<img src="https://firebasestorage.googleapis.com/v0/b/flutterdart-5d354.appspot.com/o/docs%2FMaterialButton.gif?alt=media&token=73e786a8-8639-4f34-940f-ae3497acb191"/><br/>
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
<img src="https://firebasestorage.googleapis.com/v0/b/flutterdart-5d354.appspot.com/o/docs%2FRawMaterialButton.gif?alt=media&token=9e43a5e7-f747-48de-9210-36ce65c58076"/><br/>
```dart
MaterialButton(  
  padding: EdgeInsets.symmetric(
    horizontal: 16.0, vertical: 12.0,
  ),
  color: Theme.Colors.foodieon,  
  onPressed: () { },  
  child: Text(  
    'MaterialButton',
    style: TextStyle(  
    color: Colors.white,  
    fontSize: 16.0,  
  ),
),
```
> **Note:** The **RawMaterialButton** doesn't have `shape` property as well as `color`.  `FlatButton` and `RaisedButton` is superset of `RawMaterialButton`.

## DropDownButtons
<img
src="https://firebasestorage.googleapis.com/v0/b/flutterdart-5d354.appspot.com/o/DropDownButton.gif?alt=media&token=ffb3d6b6-36ee-45c1-9b44-0d6fadd9f86b"/>
<br/>
```dart
Column(  
  children: <Widget>[  
    DropdownButton<String>(  
      items: <String>[  
        'KEY1',  
        'KEY2',  
        'KEY3',  
        'KEY4',  
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
> **Note:** To map the **DropDownButton** doesn't have `shape` property as well as `color`.  `FlatButton` and `RaisedButton` is superset of `RawMaterialButton`.
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
eyJoaXN0b3J5IjpbNTMzNTc2NTU1LDEwMzUxNjgsLTE1MzIyNz
YxNTQsLTE4NDIwMzYzOTksMTMxNzQ3NjEzMSwyMDYyMjExMzA4
LDExMjkxODE2NzEsMzgxMzg3MzRdfQ==
-->