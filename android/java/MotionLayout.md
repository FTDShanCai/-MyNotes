# MotionLayout 

```
使用版本      implementation 'androidx.constraintlayout:constraintlayout:2.0.0-beta8'

MotionLayout 既 ConstraintLayout的子类,并实现了NestedScrollingParent3接口，主要是为了使用约束布局写属性动画。
```

### MotionLayout 标签中的属性

##### app:layoutDescription 
```
关联motion xml文件
```

##### app:showPaths 
```
是否显示动画路径
```

MotionScene
----

```
声明是一个Motion Xml，固定作为父标签去使用
```

#####  app:defaultDuration
```
所有过渡的默认持续时间（以毫秒为单位）。默认持续时间用于未指定自己的持续时间的任何运动序列。
```


ConstraintSet
----

```
包含在MotionScene内
约束设置,可以理解为一个状态下的全部约束设置(约束父节点),一个约束父节点可以包含多个约束子节点
```

##### app:id 
```
为此约束父节点 设置一个id 
```

Constraint
----

```
包含在ConstraintSet内
约束子节点,对应上面，约束子节点可以指定一个约束的view，使用方法既基础布局中所有的通用xml用法与约束布局的所有用法
android:orientation
android:alpha
android:rotation
android:elevation
android:visibility
android:layout_width
android:layout_height
......等等
```

##### app:id 
```
此约束子节点 对应绑定xml中的view id （此id为布局文件中的id）
```

##### 约束子节点又可以包含 CustomAttribute、Layout、Motion、PropertySet、Transform
```
这些东西除了CustomAttribute 其他都没用过  -.= ！ 以后慢慢补充~
```

##### CustomAttribute 自定义属性
```
包含在Constraint内
app:attributeName   为此子节点的自定义属性名称 :如  BackgroundColor
app:custom....Value 这个是为了给此属性赋值,
```

Transition
----
```
包含在MotionScene内
过度操作,也很关键的一个标签,可以实现过度中的一些插值效果
```

##### app:constraintSetStart    app:constraintSetEnd
```
对应ConstraintSet id的设置,分别表示开始帧、结束帧;
```

##### app:duration 
```
帧播放时长,毫秒单位
```

OnSwipe
----
```
指定当用户在布局上滑动时要执行的操作.
动画序列的速度和目标视图的动画受滑动速度和方向的影响，具体取决于您使用可选参数设置的限制.
```

##### app:touchAnchorId
```
在滑动之后移动的视图。
```

##### app:touchAnchorSide
```
滑动所固定到的目标视图的一侧。MotionLayout 将尝试在该固定点与用户手指之间保持恒定的距离。
可接受的值包括 "left"、"right"、"top" 和 "bottom"。
```

##### app:dragDirection
```
用户滑动动作的方向。如果设置了此属性，此 <onSwipe> 将仅适用于沿特定方向的滑动。
可接受的值包括 "dragLeft"、"dragRight"、"dragUp" 和 "dragDown"。
```

OnClick
----
```
指定当用户点按特定视图时要执行的操作。
单个 <Transition> 可以具有多个 <onClick> 节点，其中每个 <onClick> 可指定一个不同的目标视图和一个在点按此视图时要执行的其他操作。
```

##### app:targetId
```
受监控的视图。当用户点按此视图时，将会发生转换。
```

##### app:ClickAction
```
点按视图时要执行的操作. 
transitionToStart 过度第一帧
transitionToEnd   过度最后一帧
jumpToStart  跳到第一帧
jumpToEnd 跳到最后一帧
toggle   开关状态
```


KeyFrameSet
----
```
指定运动序列过程中视图的位置和属性。默认情况下，运动会从初始状态逐渐进入结束状态；
通过使用 <KeyFrameSet>，您可以构建更复杂的运动。
```


KeyPosition
----
```
指定视图在运动序列中特定时刻的位置。该属性用于调整默认的运动路径。
```

##### app:motionTarget
```
其运动由此 <KeyPosition> 控制的视图。
```

##### app:framePosition
```
1 到 99 之间的整数，用于指定运动序列中视图何时到达此 <KeyPosition> 指定的点。
```

##### app:percentX  app:percentY
```
指定视图应到达的位置。 keyPositionType 属性指定如何解释这些值。
```


##### app:keyPositionType
```
指定如何解释 percentX 和 percentY 值。

parentRelative:  
percentX 和 percentY 是相对于父视图指定的。X 为横轴，范围从 0（左端）到 1（右端）。Y 为纵轴，其中 0 为顶部，1 为底部。


deltaRelative:   
percentX 和 percentY 是相对于视图在整个运动序列过程中移动的距离指定的。X 为横轴，Y 为纵轴；在这两种情况下，0 为视图在该轴上的起始位置，1 为最终位置。


pathRelative:
X 轴是目标视图在路径范围内移动的方向，其中 0 为起始位置，1 为最终位置。Y 轴垂直于 X 轴，正值位于路径左侧，负值位于右侧；
设置一个非零的 percentY 可使视图向一个方向或另一个方向呈弧形运动。因此，视图的初始位置为 (0,0)，最终位置为 (1,0)。
```
[灵魂导图](https://github.com/FTDShanCai/-MyNotes/blob/master/Images/keyPositionType_pathRelative%E5%9D%90%E6%A0%87%E8%AF%B4%E6%98%8E.png) 


KeyPosition
----
```
指定运动序列中特定时刻的视图属性。您可以使用 <KeyAttribute> 设置视图的任何标准属性。
android:visibility
android:alpha
android:elevation
android:rotation
android:rotationX
android:rotationY
transitionPathRotate
android:scaleX
android:scaleY
android:translationX
android:translationY
android:translationZ
```




