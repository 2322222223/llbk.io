### Flutter当中的Activity和Fragment是什么?

在安卓当中,	Activity代表用户可以做的几种的事情,Fragment代表用户的一种薪给或者交互.

而在Flutter当中,这两个概念都是在Widget的保护伞下的,Flutter当中的一切都是Widget,所以Widget就代表这屏幕.

可以使用Navigator在两个不同的Route之间跳转.Route代表不同页面或者是品目,或者是不同的状态或相同的数据.



### 监听生命周期

在android中,可以重写生命周期的方法, 

而在Flutter当中没有这个概念,但是可以通过挂载WidgetBinding观察监听didChangeApplifecyclerState()方法的改变来达到监听生命周期的事件的目的:

**inactive** ——应用已在活跃状态，并且还没有收到用户操作。因为在Android上没有等价的映射，所以这个事件仅仅在iOS上有效。

**paused**——应用对用户已不可见，用户操作已无效，并且在后台运行。等价于Android的`onPause()`方法。

**resume**——应用已显示并且已经可以响应用户的操作。等价于Android的`onPostResume ()`方法。

**suspending**——应用暂时处于暂停状态。这等价于Android的**onStop**；因为在iOS上没有等价的方法，所以这个方法不会在iOS上触发。

---



```dart
import 'package:flutter/widgets.dart';

class LifecycleWatcher extends StatefulWidget {
  @override
  _LifecycleWatcherState createState() => new _LifecycleWatcherState();
}

class _LifecycleWatcherState extends State<LifecycleWatcher> with WidgetsBindingObserver {
  AppLifecycleState _lastLifecyleState;

  @override
  void initState() {
    super.initState();
    WidgetsBinding.instance.addObserver(this);
  }

  @override
  void dispose() {
    WidgetsBinding.instance.removeObserver(this);
    super.dispose();
  }

  @override
  void didChangeAppLifecycleState(AppLifecycleState state) {
    setState(() {
      _lastLifecyleState = state;
    });
  }

  @override
  Widget build(BuildContext context) {
    if (_lastLifecyleState == null)
      return new Text('This widget has not observed any lifecycle changes.', textDirection: TextDirection.ltr);

    return new Text('The most recent lifecycle state this widget observed was: $_lastLifecyleState.',
        textDirection: TextDirection.ltr);
  }
}

void main() {
  runApp(new Center(child: new LifecycleWatcher()));
}
```

---

