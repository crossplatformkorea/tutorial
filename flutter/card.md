## Card
<img src="https://user-images.githubusercontent.com/73378472/200167748-c6586ec6-7413-49eb-a7f7-993389266073.png"/></br>

```dart
Card(
  margin: const EdgeInsets.symmetric(horizontal: 24),
  elevation: 10,
  child: SizedBox(
    width: double.infinity,
    height: 207,
    child: Padding(
      padding: const EdgeInsets.all(24),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          const Padding(
            padding: EdgeInsets.only(bottom: 16),
            child: Text(
              "Brand",
              style: TextStyle(
                  color: Color(0xffB3B3B3),
                  fontSize: 12,
                  fontWeight: FontWeight.w500),
            ),
          ),
          const Padding(
            padding: EdgeInsets.only(bottom: 8.0),
            child: Text(
              "Title",
              style: TextStyle(
                  color: Color(0xff262626),
                  fontSize: 16,
                  fontWeight: FontWeight.w700),
            ),
          ),
          const Padding(
            padding: EdgeInsets.only(bottom: 16),
            child: Text(
              "Content",
              style: TextStyle(
                color: Color(0xff262626),
                fontSize: 14,
              ),
            ),
          ),
          Row(
            crossAxisAlignment: CrossAxisAlignment.center,
            children: [
              Container(
                width: 16,
                height: 16,
                margin: const EdgeInsets.only(right: 4),
                decoration: const BoxDecoration(
                  color: Colors.red,
                  borderRadius: BorderRadius.all(
                    Radius.circular(6),
                  ),
                ),
                child: const Center(
                  child: Text(
                    "N",
                    style: TextStyle(color: Colors.white, fontSize: 8),
                  ),
                ),
              ),
              const Text(
                "nain93",
                style: TextStyle(
                    fontSize: 12, fontWeight: FontWeight.w700),
              ),
              Container(
                margin: const EdgeInsets.fromLTRB(4, 0, 8, 0),
                padding: const EdgeInsets.symmetric(
                    horizontal: 4, vertical: 2),
                decoration: const BoxDecoration(
                  color: Color(0xffB3B3B3),
                  borderRadius: BorderRadius.all(
                    Radius.circular(4),
                  ),
                ),
                child: const Text(
                  "실명",
                  style: TextStyle(
                      color: Colors.white,
                      fontSize: 9,
                      fontWeight: FontWeight.w700),
                ),
              )
            ],
          ),
          Container(
            margin: const EdgeInsets.fromLTRB(0, 16, 0, 8),
            child: const Divider(
              height: 1,
              color: Color(0xffF2F3F5),
            ),
          ),
          Row(
            children: [
              const Text(
                "2022/05/20 10:00:00",
                style: TextStyle(color: Color(0xffB3B3B3)),
              ),
              const Spacer(),
              Container(
                margin: const EdgeInsets.only(right: 8),
                child: const Icon(
                  Icons.remove_red_eye,
                  size: 14,
                  color: Color(0xffB3B3B3),
                ),
              ),
              const Text(
                "1",
                style: TextStyle(color: Color(0xffB3B3B3)),
              )
            ],
          )
        ],
      ),
    ),
  ),
),
```

[Card][CardLink] 위젯를 활용한 형태입니다. 프로필 정보, 상품 정보 등을 나타내는데 사용합니다 모서리를 둥글게 하기위해서 `Shape` 속성에 [RoundedRectangleBorder][RoundedRectangleBorderLink]를 줄 수도 있습니다.

[CardLink]:https://api.flutter.dev/flutter/material/Card-class.html
[RoundedRectangleBorderLink]:https://api.flutter.dev/flutter/painting/RoundedRectangleBorder-class.html