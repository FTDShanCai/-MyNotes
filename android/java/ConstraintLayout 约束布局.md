#  优化布局利器   ConstraintLayout   约束布局

```
约束布局，顾明思意通过view与view之间的约束关系达到定位的作用，据说布局相对于相对布局速度能提高30%，里面各种属性记录走一波。

implementation 'androidx.constraintlayout:constraintlayout:2.0.0-alpha3'

```

###  基础相对属性


*  layout_constraintStart_toStartOf
*  layout_constraintStart_toEndOf
*  layout_constraintEnd_toStartOf
*  layout_constraintEnd_toEndOf

*  layout_constraintLeft_toLeftOf
*  layout_constraintLeft_toRightOf
*  layout_constraintRight_toRightOf
*  layout_constraintRight_toLeftOf

##### 这一组如果敲出来其实没有什么区别，但是其实是有区别的，start 和 end相关是支持RTL布局，什么是RTL布局?[猛戳]('https://blog.csdn.net/azhengye/article/details/79460413')

##### 所以说推荐用start 和 end 相关组合，尽量不要用left 和  right



