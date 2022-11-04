# Popups

## Button Popup
<img src="https://user-images.githubusercontent.com/73378472/199906662-7b8d157a-c2e6-4326-895a-a52989988c63.gif"/><br/>

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
> [AlertDialog][AlertDialogLink]를 활용한 버튼을 추가 할 수 있는 팝업입니다. 

> [showDialog][showDialogLink]로 팝업을 띄우고 [AlertDialog][AlertDialogLink] 위젯으로 구성합니다 

> title항목과 content항목으로 나누어서 구성하고 actions 옵션에 버튼을 추가할 수 있습니다

> 바깥영역을 클릭하거나 onPressed에 Navigator.of(context).pop()를 추가해서 팝업을 끌 수 있습니다

[AlertDialogLink]: https://api.flutter.dev/flutter/material/AlertDialog-class.html
[showDialogLink]: https://api.flutter.dev/flutter/material/showDialog.html

## Toast Popup
<img src="https://user-images.githubusercontent.com/73378472/199917199-1ece735b-ffea-4065-9066-3a54ef34732d.gif"/><br/>

```dart
Center(
  child: ElevatedButton(
    child: const Text("ToastPopup"),
    onPressed: () {
      showDialog<String>(
        context: context,
        barrierColor: const Color.fromARGB(0, 0, 0, 0),
        builder: (_) => const PopupAnimation(
          duration: Duration(milliseconds: 500),
        ),
      );
    },
  ),
),

class PopupAnimation extends StatefulWidget {
  const PopupAnimation({Key? key, required this.duration}) : super(key: key);

  final Duration duration;

  @override
  State<PopupAnimation> createState() => _PopupAnimationState();
}

class _PopupAnimationState extends State<PopupAnimation>
    with SingleTickerProviderStateMixin {
  late AnimationController _controller;

  @override
  void initState() {
    super.initState();
    _controller = AnimationController(vsync: this, duration: widget.duration)
      ..forward();

    Future<void>.delayed(const Duration(seconds: 2), () {
      _controller.reverse();
    });
  }

  late final Animation<Offset> _offsetAnimation = Tween<Offset>(
    begin: const Offset(0, 0.5),
    end: Offset.zero,
  ).animate(CurvedAnimation(
    parent: _controller,
    curve: Curves.easeInOut,
  ),
);


SlideTransition(
  position: _offsetAnimation,
  child: Align(
    alignment: Alignment.bottomCenter,
    child: Container(
      margin: const EdgeInsets.only(bottom: 50),
      decoration: const BoxDecoration(
        color: Color.fromRGBO(0, 0, 0, 0.6),
        borderRadius: BorderRadius.all(Radius.circular(4),
      ),
    ),
    width: 200,
    height: 40,
    child: const Center(
      child: Text(
        "Toast",
        textAlign: TextAlign.center,
        style: TextStyle(
          fontSize: 20,
          color: Colors.white,
          fontWeight: FontWeight.w400,
          decoration: TextDecoration.none),
        ),
      ),
    ),
  ),
);

@override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }
```

> [SlideTransition][SlideTransitionLink]을 활용한 아래에서 올라오는 **ToastPopup**입니다

> [showDialog][showDialogLink] builder에 커스텀 PopupAnimation위젯으로 구성됩니다.
 
> [AnimationController][AnimationControllerLink]를 사용해 애니메이션을 적용하고 **initState()**에서 실행시키며 **dispose()**로 제거해줍니다 (controller 할당후 dispose()로 삭제해야합니다)

> 팝업이 올라오는 시간만 prop으로 받고있으나 지속시간도 커스텀하게 사용 할 수 있습니다.

> [SnackBar][SnackBarLink]위젯으로 좀 더 쉽게 구현할 수도 있습니다.

[SlideTransitionLink]:https://api.flutter.dev/flutter/widgets/SlideTransition-class.html
[AnimationControllerLink]:https://api.flutter.dev/flutter/animation/AnimationController-class.html
[SnackBarLink]:https://docs.flutter.dev/cookbook/design/snackbars

## Bottom Sheet Popup
<img src='https://user-images.githubusercontent.com/73378472/199940169-6e7d1b9c-502f-404a-9192-0bfde02dee49.gif'/><br/>

```dart
ElevatedButton(
  child: const Text("BottomSheet"),
  onPressed: () {
    showModalBottomSheet(
      context: context,
      shape: const RoundedRectangleBorder(
        borderRadius: BorderRadius.only(
          topLeft: Radius.circular(30),
          topRight: Radius.circular(30),
        ),
      ),
      builder: (_) {
        return Container(
          height: 200,
          decoration: const BoxDecoration(
              borderRadius: BorderRadius.only(
                  topLeft: Radius.circular(30),
                  topRight: Radius.circular(30))),
          child: Center(
              child: ElevatedButton(
            style: const ButtonStyle(
                backgroundColor: MaterialStatePropertyAll(Colors.red)),
            onPressed: () {
              Navigator.pop(context);
            },
            child: const Text("close modal"),
          )),
        );
      },
    );
  },
),
```

> [showModalBottomSheet][showModalBottomSheetLink]를 사용한 아래에서 올라오는 bottom sheet 팝업입니다.

> [RoundedRectangleBorder][RoundedRectangleBorderLink] shape로 borderRadius 곡선을 준 팝업입니다.

> 팝업을 종료 할때는 **onPressed**에 **Navigator.pop(context)**으로 종료합니다.

[showModalBottomSheetLink]:https://api.flutter.dev/flutter/material/showModalBottomSheet.html
[RoundedRectangleBorderLink]:https://api.flutter.dev/flutter/painting/RoundedRectangleBorder-class.html