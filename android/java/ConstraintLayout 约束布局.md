#  优化布局利器   ConstraintLayout   约束布局

```
约束布局，顾明思意通过view与view之间的约束关系达到定位的作用，据说布局相对于相对布局速度能提高30%，里面各种属性记录走一波。

implementation 'androidx.constraintlayout:constraintlayout:2.0.0-alpha3'

```


###  基础相对属性

其意思就是本布局的左或右约束在目标布局的左边或者右边

*  layout_constraintStart_toStartOf
*  layout_constraintStart_toEndOf
*  layout_constraintEnd_toStartOf
*  layout_constraintEnd_toEndOf
>> 手动分割线
*  layout_constraintLeft_toLeftOf
*  layout_constraintLeft_toRightOf
*  layout_constraintRight_toRightOf
*  layout_constraintRight_toLeftOf

##### 这一组如果敲出来其实没有什么区别，但是其实是有区别的，start 和 end相关是支持RTL布局，什么是RTL布局?[猛戳](https://blog.csdn.net/azhengye/article/details/79460413)

##### 所以说推荐用start 和 end 相关组合，尽量不要用left 和  right

除了上面左右关系的，还有下面上下关系的

*  layout_constraintTop_toTopOf
*  layout_constraintTop_toBottomOf
*  layout_constraintBottom_toBottomOf
*  layout_constraintBottom_toTopOf



###  角度依赖

* layout_constraintCircle     添加角度依赖目标
* layout_constraintCircleAngle  角度（默认0，目标上面）
* layout_constraintCircleRadius  半径



###  权重weight

* layout_constraintHorizontal_weight 水平权重
* layout_constraintVertical_weight  垂直权重



###  偏移 bias

* layout_constraintHorizontal_bias 横向偏移
* layout_constraintVertical_bias   垂直偏移

```
这个地方有需要注意的点，比如想设置横向偏移的话，必须保证约束左右的布局位置是固定的，就是不能随着别的约束目标而自己移动。
不然的话，这个属性是不会起作用的。
```



###  约束链  Chain Style

* layout_constraintHorizontal_chainStyle 横向约束链
* layout_constraintVertical_chainStyle  垂直约束链



##### 这个东西其实就是去找设置属性的这个布局的相关横向或者垂直方向的约束关系，然后去统一去设置 三个属性其中之一
```
packed  拥挤 挤在一起
spread  展开（不贴边）
spread_inside  展开(贴边)
```


### 宽高比

*  layout_constraintDimensionRatio 宽高比


### 百分比布局

*  layout_constraintWidth_percent 宽度百分比
*  layout_constraintHeight_percent 高度百分比


### 指导线  GuideLine

```
属于widget控件，可以设置方向 水平 or  垂直
可以通过水平去对齐一些文案，偏左偏右什么的。
```
*  layout_constraintGuide_percent  水平线相对于父布局的百分比
*  layout_constraintGuide_begin  水平线开始偏移距离
*  layout_constraintGuide_end  水平线结束偏移距离

### 屏障  Barrier

```
套在包含ids中所有空间的一层屏障，会根据中的ids的长度屏障会自动延长；
需要对齐屏障外的可以根据barrier的id进行约束
```

* barrierDirection 屏障方向  上下左右
* constraint_referenced_ids 屏障中控件的ids

### 组  Group

```
可以将大部分控件放进组里，对组做隐藏和显示操作，就会自动隐藏或者显示组里的成员
```

* constraint_referenced_ids  组中控件的ids



