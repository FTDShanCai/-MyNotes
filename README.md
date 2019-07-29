私藏笔记  ヾ(≧O≦)〃嗷~
=

#2019年7月12日

1、README编辑教程[外链](https://blog.csdn.net/luofeixiongsix/article/details/80841575 "外链")

2、@BindingAdapter  Application namespace for attribute app:items will be ignored.
DataBinding @BindingAdapter  注解自定义XML方法入口时，可以把(app：xxxx)修改为(xxxx)

#2019年7月25日

3、 Kotlin 相比java 比较不错的地方
| 方法的重载:
fun jointoString(s: CharSequence, a: String = "", aa: String = "")
| 扩展函数:
OkHttpClient.getConnectTimeout():Int = this.connectTimeoutMillis()
不过有局限性，不能访问私有还有内部的属性，不过可以自定义一些返回参数组合还是挺好用的。
| 扩展属性:
val String.lastChar: Char get() = get(length - 1)
和扩展函数一样，必须有get函数， 类名.后面是属性名称(此属性名为 lastChar)。
    
#2019年7月29日

3、 java中的内部类(非静态内部类)和嵌套类(静态内部类)的区别
内部类是非静态的内部类（实例化的话  A.B b = new A().new B(); ），嵌套类是静态的内部类( A.B b = new A.B(); )

4、Kotlin密封类  关键字sealed
被这个关键字sealed修饰的类即为密封类，默认当前类为open类，即可有子类，而且所有的子类实现必须存在当前类中，如果用when判断的时候编译器会自动提示出需要增加的is 子类-> //TO-DO ,方便我们忘记修改这个类使用到的地方。


