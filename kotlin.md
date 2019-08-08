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
a?.b=1      如果a为空的话，对b的赋值操作不会执行
a!!.b=1     如果a为空的话，会直接抛出异常
a?.b?:1     如果a为空的话，会走：后面的逻辑，相当于java中的try cath 个人理解。


需要注意的一些点
List<Int?>    与   List<Int>?   (要小心决定什么是可空的：集合的元素还是集合本身)这两个表示的可控性不一样，一个是List为空，但是集合中包含的元素可能为空，另外个是集合可能为空，但是包含元素肯定为Int类型

filterNotNull 扩展函数可以过滤集合中不为空的对象并返回一个对象不为空的集合

```

### kotlin 中类型系统中比较常用的一些东西
```
as            安全转换  val str = object as String
let函数       str?.let{...}  里面可以写关于str对象的一些逻辑，如果str为空的话将不会执行这部分代码。
```

### kotlin 中的集合与java中有什么区别
```
kotlin中集合分2种，只读集合(Collection)、可变集合(MutableCollection)

只读集合如字面意义，长度固定，不能增加，值只有初次复制。

可变集合就是可以增加删除集合内元素的集合，kotlin中通常用Array

kotlin中引用java代码中的集合转义为只读集合的有（List、Set、Map、Collection、Iterable等）,在kotlin中都不能进行增加和删除操作。

kotlin中引用java代码中的集合转义为可变集合的有(ArrayList、HashMap、HasSet等)，再空kotlin中都可以正常的增加或删除
```

### kotlin 中贼强的重载运算符（可以重载一元，二元，复合运算符，比较运算符不要太好用） 可以使相同类型直接做运算
```
示例：重载二元运算符 求2个人总共有多少钱

data class Man(val rmb: Int) {
   operator fun plus(other: Man): Int { //这块可以自定义 传参类型 和 返回类型
      return rmb + other.rmb  
   }
}

fun main() {
    val a = Man(1)  
    val b = Man(2)
    print(a + b) //直接用a+b返回了 2个Man对象的rmb和
}
Log:  3  

关键字 operator  重载二元运算方法必须要带的关键字

注意点：二元运算的时候是存在优先级的，比如 a+b*c  是会先计算b*c 然后再+a

可重载的一元运算符:
unaryPlus   正数      +a
unaryMinus  负数      -a
not         非        !a
inc         自增      ++a,a++
dec         自减      --a,a--

可重载的二元算术运算符：
plus    加法      a + b
minus   减法      a - b
times   乘法      a * b
div     除法      a / b
mode    取余      a % b
```

### kotlin 中对区间运算符的约定 (get、set)

Get 其实就是 X[...]

Set 其实就是 X[...] = value

```
    =======================Get的用法=======================
    data class People(val age: Int, val sex: String) 

    operator fun People.get(int: Int): String { // 重写people类的区间方法（其中的传参和返回都可以自定义）
        return when (int) {
            1 -> age.toString()    返回年龄
            2 -> sex               返回性别
            else -> "error  index error"  返回错误
        }
    }

    fun main() {
        val man = People(18, "男")
        println(man[1])
        println(man[2])
        println(man[3])
    }
    
    Log: 18
         男
         error  index error
        
   =======================Set的用法=======================
   
    data class People(var age: Int, var sex: String) //属性变成var类型 可变了。

    operator fun People.set(int: Int,value: String) { //value 就是等号后面的值
         when (int) {
            1 -> age =value.toInt()      年龄赋值
            2 -> sex=value               性别赋值
            else -> println ("error  index error"）  错误
        }
    }

    fun main() {
        val man = People(18, "男")
       man[1]= "17"   
       man[2]="女"
       println(man)
    }
    
    Log:  People(17,女)
```


### kotlin 中运算符重载的总结

| 目前为止，kotlin 中表现很多简单的运算，比如 val ints= 10..20  map["key"]  这些都是系统利用运算符重载了函数的 rangeTo ，get 等方法，其实有很多值的我们学习的运算符重载，我们可以利用当前简单的重载节省重复代码。而且更安全的处理一种类型，而往常java能给我们的只是提供公共函数去根据返回值或者一些进行判断。而kotlin是直接去修改约定、运算符的重载，这种会非常的便捷。


### kotlin 中解构声明和组件函数

解构声明：
```
    data class People(val age: Int, val sex: String)
  
  
    fun main() {
        val people = People(26,"男")
        val (age,sex) =people   // 用初始化People类相同的常量，取得people 的 age，sex的值，当然类型也是一样的
        println("$age  $sex")
    }
    
    Log: 26  男
```


###  kotlin 中的函数是可以传一个lambda 作为参数或者 已lambda作为返回值。（这种的统称高阶函数）

__高阶函数其实主要作用还是为了做代码去重，更好的复用代码块。

作为参数：
```
    定义一个lambda作为参数的numbers方法
    fun numbers(n: (Int, Int) -> Int): Int {
        val result = n(3, 3) //lambda 求值
        return result * 10 //  求值后进行的一些操作，此处乘10
    }
    
     fun main(){
        val jia: (Int, Int) -> Int = { x, y -> x + y }  
        val jian: (Int, Int) -> Int = { x, y -> x - y }
        println("${numbers(jia)}  ${numbers(jian)}")
    }

    Log： 60    0

```

作为返回值
```
    class People(val age: Int, val name: String)
    fun test() {
        val list = listOf(People(20, "张三"), People(25, "李四"))
        val n = list[0].filter(getFilter())
        print("$n")
    }
    //定义People的扩展函数filter
    fun People.filter(predicate: (People) -> Boolean): Int {
        return if (predicate(this)) 0 else 1  //如果满足函数式 返回0，不满足函数式返回1
    }
    //getFilter 函数式作为过滤条件 大于25岁的
    fun getFilter(): (People) -> Boolean {
        return { p: People -> p.age > 25 }
    }
    Log:1
```


### kotlin 内联函数 inline 

lambda表达式会被正常地编译成匿名类，这表示每次调用一次lambda表达式，一个额外的类就会被创建。并且如果lambda 捕捉了某个变量，那么每次调用的时候都会创建一个新的对象，这会给运行时带来额外的开销，导致lambda比一个直接执行的相同代码的函数效率更低，所以当当当当~~~~ ，你需要学习inline，内联函数
