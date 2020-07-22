### 路由控制
[Fluro](https://pub.flutter-io.cn/packages/fluro)
```
路由管理，还没学到....听说还挺好用;
```

### 网络请求

[Dio](https://pub.flutter-io.cn/packages/dio)
```
基本算是android 中的okhttp了。 用法简单，基于httpclient的封装；
```
### 状态共享

[Provider](https://pub.flutter-io.cn/packages/provider)  
```
利用的是InheritedWidget 对应的Element中存在 _dependents 此map（为保存状态的对象），利用_inheritedWidgets层级查找找到对应状态的widget；
而且解决了StatelessWidget中dispose释放的问题，值得推荐使用；
```

[Flutter_Bloc](https://pub.flutter-io.cn/packages/flutter_bloc)
```
 此框架没有真正试用过，实现与provider不同，好像是通过Stream来实现
```

### 异步变换
[Rxdart](https://pub.flutter-io.cn/packages/rxdart)  
```
此框架虽然还没到1.0正式版，但是对于android dev还是挺友好的，最新版本0.24.1，基本改为对stream的操作，dart中的stream本身也是非常强大的。
```

### 数据存储
[Shard_preferences](https://pub.flutter-io.cn/packages/shared_preferences)
```
字面意思就是android中的sp，缓存到本地xml文件中，算是比较轻量级的存储方式；
```

[Sqflite](https://pub.flutter-io.cn/packages/sqflite)
```
flutter 中的 Sqlite 数据库 
```
### 依赖注入
[get_it](https://pub.flutter-io.cn/packages/get_it)
```
 没用过...
```

### 工具

[fluttertoast](https://pub.flutter-io.cn/packages/fluttertoast)
```
flutter 中的吐司
```
