### 图片文件无需在.yaml文件中一个个配置
```
图片文件无需一个个配置。如图片在assets/images文件夹下，只需配置 assets/images/即可。
```


### Flutter中如何实现1像素 (1px)
```
 var px = 1 / window.devicePixelRatio;
 var px1 = 1 / (MediaQuery.of(context).devicePixelRatio);
 以上2种方式都可以
```

### 如何让flutter自动加载不同分辨率的图片资源？
```
不同分辨率的图片分别放在2.0x,3.0x等文件夹下，会自动加载。
注意：不需要1.0x文件夹但必须有1.0x的图片，比如存在image文件夹，则1.0x的图片直接放在image文件夹下，并在image文件夹下创建2.0x、3.0x文件夹，里面放入相应分辨率的图片;
```

