### Text Widget-文本组件

实例代码:

```dart
import 'package:flutter/material.dart';

void main() =>
    {runApp(new MyApp(
        
​    ))};

class MyApp extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return new MaterialApp(
      title: '',
      home:new Scaffold(
        body: new Center(
          child: new Text(
            '我的text',
            textAlign: TextAlign.center,
          ),
        ),
      ),
    );
  }
}
```



------



#### `TextAlign`对齐方式属性:

- `center`: 文本以居中形式对齐,这个也算比较常用的了。
- `left`:左对齐，经常使用，让文本居左进行对齐，效果和start一样。

- `right` :右对齐，使用频率也不算高。
- `star`t:以开始位置进行对齐，类似于左对齐。

- `end`: 以为本结尾处进行对齐，不常用。有点类似右对齐.



```dart
child:Text(  

 '我的text',  

 textAlign:TextAlign.left, )
```



------



#### `maxLines`属性限制行数:

```dart
child:Text(
  '我的text',
  textAlign:TextAlign.left,
  maxLines: 1,
)
```



---



#### `overflow`属性是用来设置文本溢出时:

- `clip`：直接切断，剩下的文字就没有了，感觉不太友好，体验性不好。
- `ellipsis`:在后边显示省略号，体验性较好，这个在工作中经常使用。

- `fad`e: 溢出的部分会进行一个渐变消失的效果，当然是上线的渐变，不是左右的哦。

------

#### 

#### `style`**属性内容比较多可以设置字体的颜色,大小,下划线等等**:

```dart
import 'package:flutter/material.dart';
void main () => runApp(MyApp());

class MyApp extends StatelessWidget{
  @override
  Widget build(BuildContext context ){
      return MaterialApp(
        title:'Text widget',
        home:Scaffold(
          body:Center(
child:Text(
  '我的text',
  textAlign:TextAlign.left,
  overflow:TextOverflow.ellipsis,
  maxLines: 1,
  style: TextStyle(
    fontSize:25.0,
    color:Color.fromARGB(255, 255, 150, 150),
    decoration:TextDecoration.underline,
    decorationStyle:TextDecorationStyle.solid,
  ),
)
          ),
        ),
      );
  }
}
```

---

