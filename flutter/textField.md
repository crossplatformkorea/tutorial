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

> **Note:** You can add other prefix or suffix.

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

> **Note:** **EditableText** is interacts with the TextInput service to let the user edit the text it contains. It also provides scrolling, selection, and cursor movement.


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
),
```

> **Note:** **TextFormField** is This is a convenience widget that wraps a TextField widget in a FormField.