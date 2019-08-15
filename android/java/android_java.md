# android 日常记录

### @BindingAdapter  Application namespace for attribute app:items will be ignored.

DataBinding @BindingAdapter  注解自定义XML方法入口时，可以把(app：xxxx)修改为(xxxx)

### MotionLayout 的使用

```
MotionLayout 是 ConstrainLayout 2.0 库中被引入的一个新类，帮助安卓开发者关联手势和组件动画。

如要使用需使用依赖:

implementation 'androidx.constraintlayout:constraintlayout:2.0.0-alpha3'

```

* MotionScene 标签的xml文件

|  其中包含Transition,ConstraintSet,StateSet

 
