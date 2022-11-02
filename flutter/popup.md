# Popups

## Default popup

```dart
ElevatedButton(
  child: const Text("DefaultPopup"),
  onPressed: () {
    showDialog<String>(
      context: context,
      builder: (BuildContext context) => AlertDialog(
        backgroundColor: Colors.white,
        title: const Text('AlertDialog'),
        content: const Text('완료 상태를 바꾸시겠습니까?'),
        actions: <Widget>[
          Center(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.stretch,
              children: [
                ElevatedButton(
                  style: const ButtonStyle(
                    backgroundColor:
                      MaterialStatePropertyAll(Colors.amber)),
                  onPressed: () => Navigator.of(context).pop(),
                  child: const Text('예'),
                  ),
                ElevatedButton(
                  onPressed: () {
                    setState(() {
                      isCompleted == true
                        ? isCompleted = false
                        : isCompleted = true;
                    });
                    Navigator.of(context).pop();
                  },
                  child: const Text('아니오'),
                ),
              ],
            ),
          )
        ],
      ),
    );
  },
),
```
