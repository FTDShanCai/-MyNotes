kotlin 
=


### README编辑教程[外链](https://blog.csdn.net/luofeixiongsix/article/details/80841575 "外链")


### @BindingAdapter  Application namespace for attribute app:items will be ignored.

DataBinding @BindingAdapter  注解自定义XML方法入口时，可以把(app：xxxx)修改为(xxxx)


### Kotlin 相比java 比较不错的地方

    | 方法的重载:
    
    fun jointoString(s: CharSequence, a: String = "", aa: String = "")
    
    | 扩展函数:
    
     OkHttpClient.getConnectTimeout():Int = this.connectTimeoutMillis()
     
     不过有局限性，不能访问私有还有内部的属性，不过可以自定义一些返回参数组合还是挺好用的。
     
    | 扩展属性:
    
     val String.lastChar: Char get() = get(length - 1)
     
     和扩展函数一样，必须有get函数， 类名.后面是属性名称(此属性名为 lastChar)。


### java中的内部类(非静态内部类)和嵌套类(静态内部类)与Kotlin的区别

内部类是非静态的内部类（实例化的话  A.B b = new A().new B(); ），嵌套类是静态的内部类( A.B b = new A.B(); )

而Kotlin的内部类必须有inner修饰，不然不算内部类，访问不到全局属性。


### Kotlin密封类  关键字sealed
被这个关键字sealed修饰的类即为密封类，默认当前类为open</br>类，即可有子类，而且所有的子类实现必须存在当前类中，如果用when判断的时候编译器会自动提示出需要增加的is 子类-> //TO-DO ,方便我们忘记修改这个类使用到的地方。


### Kotlin中的== 和 ===

java 中 == 对于基础数据类型是比较的是值，对于引用类型比较的是引用地址。 

Kotlin == 比较的是值，相当于调用equals 来比较2个值是否相等，而 === 是对比2个值的引用地址 


### Java 中的Object  和 Kotlin中的Any

java 和 kotlin 中的这2个都是最基本的类，可以代表所有类（包含null）


### equals 与 hashCode 方法

这2个方法中的一个如果需要重写的话，从编码角度来说2个是需要一起重写的。


### Kotlin 中 类委托机制 关键字by

如果想实现某些接口的类，而接口中需要实现的方法过多且与另外一个实现连多数实现方法相同时，就可以将新的实现类委托给相似的类，并重写不同的接口方法实现达成目的类。

```
   class MyCollection<T>(list: Collection<T> = ArrayList()) : Collection<T> by list {
   ......
   }
```
注意：必须为interface才能用 by 关键字 ，如果是abstract类则不能用委托机制（设计如此，具体原因未知）。


### kotlin 中的 object 和 companion object 的用法和区别

| object 关键字表示当前类为静态类，其中所有的属性和方法都为静态方法，可以加入private constructor 可以禁止实例化此类。（全局静态）

| companion object 是使用在类中，包含的为内部所有的静态属性和静态方法，其可以实现interface接口方法或属性（kotlin中接口中可以包含未实现的属性）（局部静态）

| 区别：object 修饰的类为静态类，companion object 只是局部的静态区域，object可以声明匿名内部类，比如
      ```
      view.setOnclickListener(object:View.OnClickListener{...})
      ```
    
    
### kotlin中的internal 关键字

internal修饰的属性、方法、类等 表示只在本模块内可见，模块的概念只的是当前module， IntelliJ IDEA 模块或者一个maven工程，一个gradle工程。


### kotlin中的双冒号 :: 的含义

木有看懂， 支持函数，有时候跟this:: 一起用，有时候单独用。 跨过去回头仔细研究一波


### Kotlin 比较不错的集合函数式
```
filter    过滤出来符合条件的集合。
map       根据当前集合类型转换成相等数量的另外一种类型的集合
all       如果集合内都符合条件，返回true，否则false
any       与all相反，集合中只要有任意一个符合条件 就返回true，否则false
count     获取符合条件的数量
find      获取第一个符合条件的集合对象，如果没有符合条件返回null,find 其实是调用的firstOrNull，类似的用法还有findlast，lastOrNull ,indexOfLast,indexOfFirst等。
groupBy   可以把集合按照条件进行分组，符合条件的为一组，返回值为 Map<条件类型,T> 
flatMap   可以把集合中的对象中的一个集合属性，合并所以集合中对象的这个集合属性成为一个新的集合。
flatten   平铺集合，具体使用没明白咋回事
```


### kotlin 中的延迟加载 lateinit 关键字

lateinit 属于可以延迟加载，默认是为空，用的时候前在去实例化对象，而且关键点是`lateinit不支持基本类型，因为基本类型是不包含null值，比如int 默认值是为0，所以会编译报错`


### kotlin 对空值的处理
```
a?.b=1                   如果a为空的话，对b的赋值操作不会执行
a!!.b=1                  如果a为空的话，会直接抛出异常
a?.b？:"null value" =1   如果a为空的话，会走：后面的逻辑，相当于java中的try cath 个人理解。
```

 
