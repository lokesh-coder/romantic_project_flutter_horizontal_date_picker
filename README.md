# Flutter Horizontal Date Picker

A Flutter package to create a Horizontal Date Picker. It will be useful for your awesome app.

![Demo](./demo.gif)

### Example

It supports you can create a DatePicker with flexible count of items from [begin] to [end] by [itemCount].
By [itemCount] its can split into days, hours, minutes, seconds, that makes you can use this widget in many situations.

```dart
import 'package:flutter_story_list/flutter_story_list.dart';

class _MyHomePageState extends State<MyHomePage> {
  @override
  Widget build(BuildContext context) {
    return Material(
	    child: Column(
	      children: [
	        HorizontalDatePicker(
                begin: DateTime.now(),
                end: DateTime.now().add(Duration(days: 40)),
                selected: DateTime.now(),
                onSelected: (item) {
                  //TODO something
                },
                itemBuilder: (DateTime itemValue, DateTime? selected) {
                  var isSelected =
                      selected?.difference(itemValue).inMilliseconds == 0;
                  return Text(
                    itemValue.formatted(pattern: "EEE\ndd/MM\nHH:mm:ss"),
                    style: TextStyle(
                      color: isSelected ? Colors.white : Colors.black54,
                      fontSize: 12,
                    ),
                    textAlign: TextAlign.center,
                  );
                },
                itemCount: 40,
                itemSpacing: 12,
            ),
	      ],
	    ),
    );
  }
}
```

### Development environment

```
[✓] Flutter (Channel stable, 2.0.5, on macOS 11.2.3 20D91 darwin-x64, locale en-VN)
    • Flutter version 2.0.5
    • Framework revision adc687823a (11 days ago), 2021-04-16 09:40:20 -0700
    • Engine revision b09f014e96
    • Dart version 2.12.3

[✓] Android toolchain - develop for Android devices (Android SDK version 30.0.3)
    • Platform android-30, build-tools 30.0.3
    • Java binary at: /Applications/Android Studio.app/Contents/jre/jdk/Contents/Home/bin/java
    • Java version OpenJDK Runtime Environment (build 1.8.0_242-release-1644-b3-6915495)
    • All Android licenses accepted.

[✓] Xcode - develop for iOS and macOS
    • Xcode at /Applications/Xcode_12.app/Contents/Developer
    • Xcode 12.4, Build version 12D4e
    • CocoaPods version 1.10.1

[✓] Chrome - develop for the web
    • Chrome at /Applications/Google Chrome.app/Contents/MacOS/Google Chrome

[✓] Android Studio (version 4.1)
    • Android Studio at /Applications/Android Studio.app/Contents
    • Flutter plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/6351-dart
    • Java version OpenJDK Runtime Environment (build 1.8.0_242-release-1644-b3-6915495)
```