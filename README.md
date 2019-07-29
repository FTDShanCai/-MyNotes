私藏笔记  ヾ(≧O≦)〃嗷~
=

#2019年7月12日

1、README编辑教程[外链](https://blog.csdn.net/luofeixiongsix/article/details/80841575 "外链")

2、@BindingAdapter  Application namespace for attribute app:items will be ignored.</br>
DataBinding @BindingAdapter  注解自定义XML方法入口时，可以把(app：xxxx)修改为(xxxx)</br>

#2019年7月25日</br>

3、 Kotlin 相比java 比较不错的地方</br>
    | 方法的重载:</br>
    fun jointoString(s: CharSequence, a: String = "", aa: String = "")</br>
    | 扩展函数:</br>
     OkHttpClient.getConnectTimeout():Int = this.connectTimeoutMillis()</br>
     不过有局限性，不能访问私有还有内部的属性，不过可以自定义一些返回参数组合还是挺好用的。</br>
    | 扩展属性:</br>
         val String.lastChar: Char get() = get(length - 1)</br>
     和扩展函数一样，必须有get函数， 类名.后面是属性名称(此属性名为 lastChar)。</br>
    
#2019年7月29日</br>

3、 java中的内部类(非静态内部类)和嵌套类(静态内部类)的区别</br>
内部类是非静态的内部类（实例化的话  A.B b = new A().new B(); ），嵌套类是静态的内部类( A.B b = new A.B(); )</br>


