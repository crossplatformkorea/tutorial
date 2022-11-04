# TextFields

## Edit TextField
<img src="https://user-images.githubusercontent.com/73378472/199053962-fdec91a7-b776-47a3-b54b-951712cacc1f.gif"/><br/>

```dart
TextField(
  onChanged: (_) {},
  cursorColor: Colors.black,
  keyboardType: TextInputType.emailAddress,
  obscureText: false,
  enableSuggestions: true,
  autocorrect: true,
  decoration: InputDecoration(
  contentPadding: const EdgeInsets.symmetric(horizontal: 10),
  enabledBorder: OutlineInputBorder(
    borderRadius: BorderRadius.circular(8),
    borderSide: const BorderSide(color: Colors.red)),
  focusedBorder: OutlineInputBorder(
    borderRadius: BorderRadius.circular(8),
    borderSide: const BorderSide(color: Colors.blue)),
  hintText: "Edit TextField"),
),
```
> 사용자에게 입력값을 받을 수 있는 기본 **TextField**입니다. 

> **keyboardType**으로 키보드형태를 변경할 수 있고 **hintText** 옵션으로 어떤 입력값을 넣어야하는지 알려 줄 수 있습니다.

- 문서: https://api.flutter.dev/flutter/material/TextField-class.html

## Search TextField
<img src="https://user-images.githubusercontent.com/73378472/199053965-4dcad9e7-c543-4514-87f5-0c780439c5b7.gif"/><br/>

```dart
TextField(
  onChanged: (_) {},
  decoration: InputDecoration(
  contentPadding: const EdgeInsets.symmetric(horizontal: 10),
  prefixIcon: IconButton(
    onPressed: () {}, 
    icon: const Icon(Icons.search)),
  prefixIconColor: Colors.black,
  suffixIcon: TextButton(
    onPressed: () {},
    child: const Text(
    "Search",
    style: TextStyle(
    color: Color(0xFF262626), fontWeight: FontWeight.w700),
    ),
  ),
  hintText: "Search TextField"),
),
```

> **TextField**에서 옵션만 추가된 형태로 prefix, suffix 옵션을 추가해서 입력값이외에 TextField안에 widget을 추가할 수 있습니다.

- 참고: prefixText 또는 suffixText의 경우 TextField에서 포커스 아웃 됐을때 사라지므로 포커스 아웃됐을때도 유지하고 싶다면  
prefixIcon 또는 suffixIcon child Text를 넣어줘야 합니다.

## Editable Text
<img src="https://user-images.githubusercontent.com/73378472/199053956-295a1eb7-f5db-4c41-9eca-6d2cf5b6140b.gif"/><br/>

```dart
Column(
  children: [
    Expanded(
      child: Container(
      padding: const EdgeInsets.all(20),
      decoration: BoxDecoration(border: Border.all()),
      child: EditableText(
        expands: true,
        minLines: null,
        maxLines: null,
        controller: TextEditingController(),
        focusNode: FocusNode(),
        style: const TextStyle(fontSize: 16, color: Colors.black),
        cursorColor: Colors.amber,
        backgroundCursorColor: Colors.green),
      ),
    ),
  ],
)
```

> **EditableText**은 multiline으로 글을 입력하고 편집 할 수 있어서 여러줄을 입력받고 편집 해야하는 ui에 적합합니다.

> focusNode, controller, cursorColor, backgroundCursorColor 옵션을 필수로 제공해주어야 합니다.

- 문서: https://api.flutter.dev/flutter/widgets/EditableText-class.html


## Text FormField
<img src="https://user-images.githubusercontent.com/73378472/199053969-2ead98c8-8c4c-491a-9549-b1b1480ba0f8.png" width="200"/><br/>

```dart
TextFormField(
  initialValue: "initialValue",
  keyboardType: TextInputType.emailAddress,
  maxLines: null,
  maxLength: null,
  decoration: const InputDecoration(
    hintText: "TextFormField",
    border: OutlineInputBorder(),
    ),
  onChanged: (_) {},
  validator: (_) {},
  onFieldSubmitted: (_) {},
),
```

> **TextField**위젯에 FormField가 덮어씌워진 위젯으로 **validator**옵션으로 유효성을 검사해 에레메세지를 띄우거나
**onFieldSubmitted**옵션으로 키보드 엔터가눌렸을때 핸들링이 가능합니다.

> 또한 컨트롤러 가 지정되지 않은 경우 **initialValue** 를 사용하여 자동으로 생성된 컨트롤러에 초기 값을 제공할 수 있습니다.

- 문서: https://api.flutter.dev/flutter/material/TextFormField-class.html
