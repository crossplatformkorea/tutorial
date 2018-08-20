# Buttons


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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDIwMzYzOTksMTMxNzQ3NjEzMSwyMD
YyMjExMzA4LDExMjkxODE2NzEsMzgxMzg3MzRdfQ==
-->