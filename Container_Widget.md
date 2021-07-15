## Container - Widget

#### Container是经常使用的控件,是一个容器,在HTML中相当于一个<div>标签 

####  Alignment属性:

作用是方便进行布局,这个属性针对的是container总的child的对齐方式,也就是容器内子控件的对齐方式,并不是container本身的对齐方式

- `bottomCenter`:下部居中对齐。
- `botomLeft`: 下部左对齐。
- `bottomRight`：下部右对齐。
- `center`：纵横双向居中对齐。
- `centerLeft`：纵向居中横向居左对齐。
- `centerRight`：纵向居中横向居右对齐。
- `topLeft`：顶部左侧对齐。
- `topCenter`：顶部居中对齐。
- `topRight`： 顶部居左对齐。

实例代码:

```dart
class MyApp extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: '',
      home: new Scaffold(
        body: new Center(
          child: new Container(
            child: new Text(
              '我是一个文本',
              style:new TextStyle(
                fontSize: 18.0,
                color: Colors.blue
              ),
            ),
            alignment: Alignment.centerRight,
          ),
        ),
      ),
    );
  }
}
```

---

#### 设置Container的宽-高-颜色等属性:

如设置宽500,高400,颜色蓝色

实例代码:

```dart
child:Container(
  child:new Text('我是一个文本',style: TextStyle(fontSize: 40.0),),
  alignment: Alignment.center,
  width:500.0,
  height:400.0,
  color: Colors.lightBlue,
),
```

#### padding属性:

padding属性是一个内边距,指Container边缘和child中的内容的间距

```dart
child:Container(
  child:new Text('我是一个文本',style: TextStyle(fontSize: 40.0),),
  alignment: Alignment.topLeft,
  width:500.0,
  height:400.0,
  color: Colors.lightBlue,
  padding:const EdgeInsets.all(10.0),
  padding:const EdgeInsets.fromLTRB(10.0,100.0,0.0,0.0)
),
```

- EdgeInsets.all(10.0)会为每一个方向加10的padding值
- EdgeInsets.fromLTRB(10.0,100.0,0.0,0.0) 会为对应的left加10,top加100的padding值

#### margin属性:

marin属性是外边距,是指Container和外部元素的间距

```dart
 child: new Container(
            child: new Text(
              '我是一个文本',
              style:new TextStyle(
                fontSize: 18.0,
                color: Colors.blue
              ),
            ),
            alignment: Alignment.topLeft,
            width: 500.0,
            height: 400.0,
            color: Colors.red,
            padding: const EdgeInsets.fromLTRB(30.0, 10.0, 0.0, 0.0),
            margin: const EdgeInsets.fromLTRB(10.0,20.0,30.0,40.0),
          ),
```

使用方式和padding一致

#### decoration属性(decoration属性与color会冲突,如果设置了color就不要设置这个):

decorration是Container的修饰器主要是设置背景和边框:

如果那个给背景加一个渐变的效果,可以使用BoxDecoration这个类,

要添加边框使用 ```border:Border.all(width:2.0,color:Colors.red)```

```dart
child:Container(
  child:new Text('我是一个文本',style: TextStyle(fontSize: 40.0),),
  alignment: Alignment.topLeft,
  width:500.0,
  height:400.0,
  padding:const EdgeInsets.fromLTRB(10.0,30.0,0.0,0.0),
  margin: const EdgeInsets.all(10.0),
  decoration:new BoxDecoration(
    gradient:const LinearGradient(
      colors: [Colors.black,Colors.black54,Colors.black12]
    )
  ),
),
```

---

