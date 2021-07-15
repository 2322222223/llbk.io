### Image - Widget 

#### image图片组件,主要有四种加载方式:

- **Image.asset**:加载资源图片，就是加载项目资源目录中的图片,加入图片后会增大打包的包体体积，用的是相对路径。

- **Image.network**:网络资源图片，意思就是你需要加入一段[http://xxxx.xxx的这样的网络路径地址。](http://xxxx.xn--xxx-lq6eyc874dnzo140aba474s0eb988h4gf./)

- **Image.file**:加载本地图片，就是加载本地文件中的图片，这个是一个绝对路径，跟包体无关。

- **Image.memory**: 加载Uint8List资源图片,这个目前用的少

  

以network的加载方式为例:

```dart
 child: new Container(
            child: new Image.network(
              "https://img1.baidu.com/it/u=3696765064,121101387&fm=26&fmt=auto&gp=0.jpg",
              scale: 1.0,
            ),
            width: 500.0,
            height: 250.0,
            color: Colors.black,
          ),
```

一般你概况下我们需要设置容器的宽高来适配图片

#### fit属性:

fit可以控制图片的拉伸和挤压,图片根据父容器来调整:

- **BoxFit.fill**:全图显示，图片会被拉伸，并充满父容器。
- **BoxFit.contain**:全图显示，显示原比例，可能会有空隙。
- **BoxFit.cover**：显示可能拉伸，可能裁切，充满（图片要充满整个容器，还不变形）。
- **BoxFit.fitWidth**：宽度充满（横向充满），显示可能拉伸，可能裁切。
- **BoxFit.fitHeight** ：高度充满（竖向充满）,显示可能拉伸，可能裁切。
- **BoxFit.scaleDown**：效果和contain差不多，但是此属性不允许显示超过源图片大小，可小不可大。

示例代码:

```dart
 body: new Center(
          child: new Container(
            child: new Image.network(
              "https://img0.baidu.com/it/u=4033867824,4154872129&fm=26&fmt=auto&gp=0.jpg",
              scale: 1.0,
              //fit: BoxFit.fill,
              //fit: BoxFit.contain,
              //fit: BoxFit.cover,
              fit: BoxFit.contain,
            ),
            width: 500.0,
            height: 250.0,
            color: Colors.black,
          ),
        ),
```

#### colorBlendMode 图片的混合模式:

- color：是要混合的颜色，如果你只设置color是不起作用的。
- colorBlendMode:是混合模式，相当于我们如何混合。

- colorBlendMode和Color配合使用,可以修改图片的颜色, 类似于滤镜,BlendMode有很多重模式,具体可以查看官方api或者运行看效果:

```dart
 child: new Container(
            child: new Image.network(
              "https://img0.baidu.com/it/u=4033867824,4154872129&fm=26&fmt=auto&gp=0.jpg",
              scale: 1.0,
              //fit: BoxFit.fill,
              //fit: BoxFit.contain,
              //fit: BoxFit.cover,
              fit: BoxFit.contain,
              color: Colors.black,
              colorBlendMode: BlendMode.difference,
            ),
            width: 500.0,
            height: 250.0,
            color: Colors.black,
          ),
```

#### repeat图片重复:

可以使图片横向后者纵向或者满屏的铺满屏幕:

- ImageRepeat.repeat : 横向和纵向都进行重复，直到铺满整个画布。
- ImageRepeat.repeatX: 横向重复，纵向不重复。
- ImageRepeat.repeatY：纵向重复，横向不重复。

示例代码:

```dart
 child: new Container(
            child: new Image.network(
              "https://img0.baidu.com/it/u=4033867824,4154872129&fm=26&fmt=auto&gp=0.jpg",
              scale: 1.0,
              //fit: BoxFit.fill,
              //fit: BoxFit.contain,
              //fit: BoxFit.cover,
              fit: BoxFit.contain,
              color: Colors.black,
              colorBlendMode: BlendMode.difference,
              //repeat: ImageRepeat.repeatY,
              repeat: ImageRepeat.repeat,
              //repeat: ImageRepeat.repeatX,
            ),
            width: 500.0,
            height: 250.0,
            color: Colors.black,
          ),
```

---

#### 通过Image.asset显示本地图片:

待续...