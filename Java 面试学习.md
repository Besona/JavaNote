## 1. 概念

### 1.1 说一下 Java 的特点
1. 平台无关性
    Java "编写一次, 到处运行". 
    Java 编译器将源代码编译成字节码 (bytecode), 字节码可以在任何安装 Java 虚拟机 (JVM) 的系统上运行.
2. 面向对象
    Java 是一门严格面向对象编程的语言, 几乎一切都是对象. 
    面向对象编程 (OOP) 特性使得代码更易于维护和重用, 包括:
        类 (class)
        对象 (object)
        抽象 (abstraction)
        封装 (encapsulation)
        继承 (inheritance)
        多态 (polymorphism)
3. 内存管理
    Java 有自己的垃圾回收机制, 自动管理内存和回收不再使用的对象. 
    这样开发者就不用手动管理内存, 减少内存泄漏和其他内存相关问题. 

### 1.2 Java 的优势和劣势都是什么?
1. 优势
    1. 跨平台
        因为 JVM 的存在, 一次编写到处运行.
    2. 面向对象
        Java 的设计从一开始就是 OOP 的.
    3. 生态强大
        比如 Spring 框架, Hibernate, 各种库和工具, 社区支持大, 企业应用广泛. 
    4. 内存管理
        自动垃圾回收机制, 减少内存泄露问题, 对开发者友好. 
    5. 多线程支持
        内置线程机制, 方便并发编程. 
    6. 安全性
        Java 有安全模型, 比如沙箱机制, 适合网络环境
    7. 稳定性
        企业级应用长期使用, 版本更新也比较注重向后兼容. 

2. 劣势
    1. 性能
        虽然 JVM 优化了很多, 但相比 C++ 或者 Rust 这种原生编译语言, 还是有一定开销. 
        特别是启动时间, 比如微服务场景下, 可能不如 Go 之类的快.
    2. 语法繁琐
        比如样板代码多, 之前没有 lambda 的时候更麻烦, 现在有了但比起 Python 还是不够简洁.
    3. 内存消耗
        JVM 本身占内存, 对于资源有限的环境可能不太友好.
    4. 面向对象过于严格
        有时候写简单程序反而麻烦, 虽然 Java8 引入了函数式编程, 但不如其他语言自然.
    5. 开发效率
        相比动态语言如 Python, Java 需要更多代码, 编译过程也可能拖慢开发节奏.

### 1.3 Java 为什么是跨平台的?
Java 能支持跨平台, 主要依赖于 JVM.
    跨平台的是 Java 程序, 不是 JVM. JVM 是用 C/C++ 开发的.
    JVM 也是一个软件, 不同的平台有不同的版本. 我们编写的 Java 源码, 编译后会生成一种 .class 文件, 称为字节码文件.
    编译生成的字节码不能直接运行, 必须通过 JVM 翻译成机器码才能运行. 不同平台下编译生成的字节码是一样的, 但是由 JVM 翻译成的机器码却不一样. 
    也就是说, 只要在不同平台上安装对应的 JVM, 就可以运行字节码文件, 运行 Java 程序. 
    即使将 Java 程序打包成可执行文件 (如 .exe), 仍然需要 JVM 的支持.
    这个过程中 Java 程序没有做任何改变, 仅仅是通过 JVM 这一 "中间层", 就能在不同平台上运行, 真正实现了 "一次编译, 到处运行".
    
### 1.4 JVM, JDK, JRE 三者的关系?
JDK > JRE > JVM
1. JVM
    JVM 是 Java 虚拟机, 是Java程序运行的环境. 
    它负责将 Java 字节码 (由 Java 编译器生成) 解释或编译成机器码, 并映射到本地的 CPU 指令集和 OS 的系统调用执行程序. 
    JVM 提供了内存管理, 垃圾回收, 安全性等功能, 使得 Java 程序具备跨平台性. 

2. JDK
    JDK 是 Java 开发工具包, 是开发 Java 程序所需的工具集合. 
    它包含了 JVM, 编译器 (javac) 调试器 (jdb) 等开发工具, 以及一系列的类库 (如 Java 标准库和开发工具库). 
    JDK 提供了开发, 编译, 调试和运行 Java 程序所需的全部工具和环境.

3. JRE
    JRE 是 Java 运行时环境, 是 Java 程序运行所需的最小环境.
    它包含了 JVM 和一组 Java 类库, 用于支持 Java 程序的执行.
    JRE 不包含开发工具, 只提供 Java 程序运行所需的运行环境.

### 1.5 JVM 和 Java 有什么区别?
Java 是语言, JVM 是平台. 一个是写代码的工具, 一个是跑代码的环境, 两者分工不同但相互配合.
    Java 是一门编程语言, 像 String, List 这些都是 Java 语言提供的.
    而 JVM 是 Java 虚拟机, 它是用来运行 Java 程序的运行环境.
    我们用 Java 语言写代码, 但代码不能直接运行, 得先通过编译器编译成字节码, 也就是 .class 文件, 然后 JVM 再把这些字节码翻译成机器能懂的指令去执行.
    Java 能够跨平台, 也就是 "一次编译，到处运行". 这个跨平台能力其实主要是 JVM 提供的. 我们写好的 Java 代码编译成字节码后, 这份字节码可以在不同操作系统上的 JVM 运行. 
    虽然底层操作系统不一样, 但因为有 JVM 这一层, 它帮我们屏蔽了这些差异, 做好了适配. 
    所以本质上是 JVM 依赖平台, 但 Java 字节码不依赖平台.

再简单说说它们和其他概念的关系.
    JDK是开发工具包, 里面有编译器, 调试工具这些, 也包含了 JRE.
    JRE 是运行环境, 包含了 JVM 和 Java 的核心类库. 
    所以关系就是 JDK > JRE > JVM. 
    如果要开发 Java 程序就得装 JDK; 而如果只是运行别人写好的程序, 装个 JRE 就够了.

还有一点, JVM 其实不只能跑 Java.
    因为 JVM 执行的是字节码, 所以像 Kotlin, Scala 这些语言, 虽然语法跟 Java 不一样, 但编译后也是生成 Java 字节码, 一样可以在 JVM 上运行.
    所以 JVM 现在已经不只是 Java 的专属了, 而是整个 JVM 语言生态的基础平台.

### 1.6 为什么 Java 解释和编译都有?
首先在 Java 经过编译之后生成字节码文件, 接下来进入 JVM 中, 就有两个步骤编译和解释.
    编译性:
        Java 源代码首先被编译成字节码, JIT 会把编译过的机器码保存起来, 以备下次使用.
    解释性:
        JVM 中一个方法调用计数器, 当累计计数大于一定值的时候, 就使用 JIT 进行编译生成机器码文件.
        否则就是用解释器进行解释执行, 然后字节码也是经过解释器进行解释运行的.
所以 Java 既是编译型也是解释性语言, 默认采用的是解释器和编译器混合的模式.

### 1.7 编译型语言和解释型语言的区别?
编译型语言: 
    在程序执行之前, 整个源代码会被编译成机器码或者字节码, 生成可执行文件. 执行时直接运行编译后的代码, 速度快, 但跨平台性较差.
解释型语言:
    在程序执行时, 逐行解释执行源代码, 不生成独立的可执行文件. 通常由解释器动态解释并执行代码, 跨平台性好, 但执行速度相对较慢.
典型的编译型语言如 C, C++, 典型的解释型语言如 Python, JavaScript.

### 1.8 Python 和 Java 的区别是什么?
Java 是一种已编译的编程语言, Java 编译器将源代码编译为字节码, 而字节码则由 Java 虚拟机执行.
Python 是一种解释语言, 翻译时会在执行程序的同时进行翻译.

### 1.9 值传递和引用传递的区别?
在 Java 中, 参数传递只有值传递一种方式, 不存在真正的 "引用传递". 
    但很多人会混淆这两个概念, 核心区别在于传递的是 "值的副本" 还是 "引用的副本".

值传递 (Pass by Value). 传递的是实际值的副本, 适用于基本数据类型 (如 int, char 等), 修改方法内的参数副本, 不会影响原变量的值.
而关于引用传递 (本质仍然是值传递), 对于对象 (引用类型), 传递的是对象引用的副本 (而非对象本身). 
两个引用 (原引用和副本) 指向同一个对象, 因此通过副本修改对象内部数据, 会影响原对象. 但如果修改副本的指向 (如重新赋值), 则不会影响原引用的指向. 

简单来说, Java 中所有参数传递都是值传递. 
    基本类型传递 "值的副本", 修改副本不影响原值
    引用类型传递 "引用的副本" 通过副本可修改对象内容, 但无法改变原引用的指向.

## 2. 数据类型
### 2.1 八种基本数据类型
Java 支持数据类型分为两类: 基本数据类型和引用数据类型.
    基本数据类型共有 8 种, 可以分为三类:
        数值型: 整数类型 (byte, short, int, long) 和浮点类型 (float, double)
        字符型: char
        布尔型: boolean
    8 种基本数据类型的默认值, 位数, 取值范围, 如下表所示:
        见 ![](https://www.xiaolincoding.com/interview/java.html#%E5%85%AB%E7%A7%8D%E5%9F%BA%E6%9C%AC%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
    
    float 和 double 的最小值和最大值都是以科学记数法的形式输出的, 结尾的 "E + 数字" 表示 E 之前的数字要乘以 10 的多少倍. 
        比如 3.14E3 就是 3.14 × 1000 = 3140, 3.14E-3 就是 3.14/1000 = 0.00314.
    
注意一下几点:
    1. Java 八种基本数据类型的字节数: 1 字节 (byte, boolean), 2 字节 (short, char), 4 字节 (int, float), 8 字节 (long, double)
    2. 浮点数的默认类型为 double (如果需要声明一个常量为 float 型, 则必须要在末尾加上 f 或 F)
    3. 整数的默认类型为 int (声明 long 型在末尾加上 l 或者 L)
    4. 八种基本数据类型的包装类: 除了 char 的是 Character, int 类型的是 Integer, 其他都是首字母大写
    5. char 类型是无符号的, 不能为负, 所以是 0 开始的.

### 2.2 int 和 long是多少位, 多少字节的?
int 类型是 32 位 (bit), 占 4 个字节 (byte). 
    int 是有符号整数类型, 其取值范围是从 -2^31 到 2^31-1. 
    例如, 在一个简单的计数器程序中，如果使用 int 类型来存储计数值, 它可以表示的最大正数是 2,147,483,647。如果计数值超过这个范围, 就会发生溢出, 导致结果不符合预期.

long 类型是 64 位, 占 8 个字节.
    long 类型也是有符号整数类型, 它的取值范围是从 -2^63 到  2^63 -1.
    在处理较大的整数数值时, 如果 int 类型的取值范围不够, 就需要使用 long 类型.
    例如, 在一个文件传输程序中, 文件的大小可能会很大, 使用 int 类型可能无法准确表示, 而 long 类型就可以很好的处理这个情况. 

### 2.3 long 和 int 可以互转吗?
可以. Java 中的 long 和 int 是可以互相转换的. 
    由于 long 类型的范围比 int 类型大, 因此将 int 转换为 long 是安全的, 但 long 转换为 int 可能会导致数据丢失或溢出. 

将 int 转换为 long 可以用直接赋值或强制类型转换来实现. 
将 long 转换为 int 需要用强制类型转换, 但需要注意潜在的数据丢失或溢出问题. 
    将 long 转换为 int 的时候, 如果 longValue 的值超出了 int 类型的范围, 转换结果将是截断之后的低位部分. 
    因此在进行转换前, 建议先检查 longValue 的值是否在 int 类型的范围内, 以避免数据丢失或溢出的问题. 

### 2.4 数据类型转换方式你知道哪些
1. 自动类型转换 (隐式转换): 当目标类型的范围大于源类型时, Java 会自动将源类型转换为目标类型, 不需要显式的类型转换.
    例如, 将 int 转为 long, 将 float 转换为 double 等. 
2. 强制类型转换 (显式转换): 当目标类型的范围小于源类型时, 需要使用强制类型转换将源类型转换为目标类型. 这可能导致数据丢失或溢出.
    例如, 将 long 转为 int, 将 double 转换为 float 等. 
3. 字符串转换: Java 提供了将字符串表示的数据转换为其他类型数据的方法.
    例如, 将字符串转换为整型 int, 可以用 Integer.parseInt() 方法; 将字符串转换为浮点型 double, 可以使用 Double.parseDouble() 方法等. 
4. 数值之间的转换: Java 提供了一些数值类型之间的转换方法, 如将整型转换为字符型, 将字符型转换为整型等. 
    这些转换方式可以通过类型的包装类来实现, 例如 Character 类, Integer 类等提供了相应的转换方法. 

### 2.5 类型互转会出现什么问题吗?
1. 基本数据类型转换的问题
    当把小范围数据类型赋值给大范围数据类型时, Java 会自动进行类型转换, 这种转换一般是安全的.
    但是大范围数据类型赋值给小范围数据类型时, 会发生数据数据溢出或者精度损失的问题.
        数据溢出: 如果大范围数据类型赋值给小范围数据类型时, 当目标类型无法容纳原数据时, 就会发生数据溢出.
            比如下 byte 类型的取值范围是 - 128 到 127. 300 的二进制表示为 00000001 00101100, 强制转换为 byte 类型时, 会丢弃高位字节, 只保留低位的 8 位 00101100, 其十进制是 44.
        精度损失: 在进行浮点数类型的转换时, 可能会发生精度损失. 由于浮点数的表示方式不同, 将一个单精度浮点数 (float) 转换为双精度浮点数 (double) 时, 精度可能会损失; 如果 double 转换为 int 也会发生精度损失的问题.

2. 对象引用转换的问题
    向上转型是自动进行的, 而且是安全的. (子类的对象转为父类的对象)
    但是向下转型需要手动进行, 并且存在风险. 如果父类对象实际上并不是目标子类的实例, 在转型时就会抛出异常.
        原因是 Java 的对象在运行时会记录其真实类型, 当进行向下转型时,Java 会检查对象的实际类型是否与目标类型兼容. 如果不兼容, 就会抛出 ClassCastException
    解决方式是需要使用 instanceof 检查

### 2.6 为什么用 bigDecimal, 不用 double?
double 会出现精度丢失的问题.
    double 执行的是二进制浮点运算, 二进制有些情况下不能准确的表示一个小数. 二进制表示小数的时候只能够表示能够用 1/(2^n) 的和的任意组合, 但是 0.1 不能够精确表示, 因为它不能够表示成为 1/(2^n) 的和的形式.

可以看到在 Java 中进行浮点数运算的时候, 会出现丢失精度的问题.
    我们如果在进行商品价格计算的时候, 就会出现问题. 很有可能造成我们手中有 0.06 元, 却无法购买一个 0.05 元和一个 0.01 元的商品.
    因为他们两个的总和为 0.060000000000000005.
    这无疑是一个很严重的问题, 尤其是当电商网站的并发量上去的时候, 出现的问题将是巨大的. 可能会导致无法下单, 或者对账出现问题.

而 Decimal 是精确计算, 所以一般牵扯到金钱的计算, 都使用 bigDecimal.

```Java
public class BigDecimalExample {
    public static void main(String[] args) {
        BigDecimal num1 = new BigDecimal("0.1");
        BigDecimal num2 = new BigDecimal("0.2");

        BigDecimal sum = num1.add(num2);
        BigDecimal product = num1.multiply(num2);

        System.out.println("Sum: " + sum);
        System.out.println("Product: " + product);
    }
}
```

在上述代码中创建了两个 BigDecimal 对象 num1 和 num2, 分别表示 0.1 和 0.2 这两个十进制数. 
    然后使用 add() 方法计算二者之和, 用 multiply() 方法计算二者乘积. 
    这样使用的 BigDecimal 可以确保精确的十进制数值计算, 避免了使用 double 可能出现的舍入误差. 
    需要注意的是, 在创建 BigDecimal 对象时, 应该使用字符串作为参数, 而不是直接使用浮点数值, 以避免浮点数精度丢失.

### 2.7 装箱和拆箱都是什么? 
装箱 (Boxing) 和拆箱 (Unboxing) 是将基本数据类型和对应的包装类之间进行转换的过程.

```Java
Integer i = 10;  //装箱
int n = i;   //拆箱
```

自动装箱主要发生在两种情况, 一种是赋值时, 另一种是在方法调用的时候.
    1. 赋值时
        这是最常见的一种情况, 在 Java 1.5 以前我们需要手动地进行转换才行, 而现在所有的转换都是由编译器来完成.
    2. 方法调用时
        当我们在方法调用时, 我们可以传入原始数据值或者对象, 同样编译器会帮我们进行转换.
            show 方法接受 Integer 对象作为参数. 当调用 show(3) 时, 会将 int 值转换成对应的 Integer 对象, 这就是所谓的自动装箱. 
            show 方法返回 Integer 对象, 而 int result = show(3); 中 result 为 int 类型, 所以这时候发生自动拆箱操作, 将 show 方法返回的 Integer 对象转换成 int 值. 

自动装箱的弊端
    自动装箱有一个问题, 那就是在一个循环中进行自动装箱操作的情况, 如下面的例子就会创建多余的对象, 影响程序的性能.
        上面的代码 sum += i; 可以看成 sum = sum + i; 但是 + 操作符不适用于 Integer 对象
        首先 sum 进行自动拆箱操作, 进行数值相加, 最后发生自动装箱曹祖哟转换成 Integer 对象. 
        由于这里我们声明的 sum 为 Integer 类型, 在上面的循环中会创建将近 4000 个无用的 Integer 对象, 在这样庞大的循环中, 会降低程序的性能并且加重了垃圾回收的工作量. 
        因此我们在编程中需要正确的声明变量类型, 避免因为自动装箱引起的性能问题. 

### 2.8 Java 为什么要有 Integer?
Integer 对应是 int 类型的包装类, 就是把 int 类型包装成 Object 对象.
    对象封装有很多好处, 可以把属性也就是数据跟处理这些数据的方法结合在一起. 
    比如 Integer 就有 parseInt() 等方法来专门处理 int 型相关的数据.

另一个非常重要的原因就是在 Java 中绝大部分方法或类都是用来处理类类型对象的
    如 ArrayList 集合类就只能以类作为他的存储对象, 而这时如果想把一个 int 型的数据存入 list 是不可能的, 必须把它包装成类, 也就是 Integer 才能被 List 所接受.

所以 Integer 存在是很必要的.

1. 泛型中的应用
    在 Java 中, 泛型只能使用引用类型, 而不能使用基本类型.
    因此, 如果要在泛型中使用 int 类型, 必须使用 Integer 包装类. 
        例如, 假设我们有一个列表, 我们想要将其元素排序, 并将排序结果存储在一个新的列表中. 
        如果我们使用基本数据类型 int, 无法直接使用 Collections.sort() 方法. 
        但是, 如果我们使用 Integer 包装类, 我们就可以轻松地使用 Collections.sort() 方法.

```Java
List<Integer> list = new ArrayList<>();
list.add(3);
list.add(1);
list.add(2);
Collections.sort(list);
System.out.println(list);
```

2. 转换中的应用
    在 Java 中, 基本类型和引用类型不能直接进行转换, 必须使用包装类来实现.
        例如, 将一个 int 类型的值转换为 String 类型, 必须首先将其转换为 Integer 类型, 然后再转换为 String 类型.

```Java
int i = 10;
Integer integer = new Integer(i);
String str = integer.toString();
System.out.println(str);
```  

3. 集合中的应用
    Java 集合中只能存储对象, 而不能存储基本数据类型. 
    因此, 如果要将 int 类型的数据存储在集合中, 必须使用 Integer 包装类.
        例如, 假设我们有一个列表, 我们想要计算列表中所有元素的和. 如果我们使用基本数据类型 int, 我们需要使用一个循环来遍历列表, 并将每个元素相加.
        但是, 如果我们使用 Integer 包装类, 我们可以直接使用 stream() 方法来计算所有元素的和.

```Java
List<Integer> list = new ArrayList<>();
list.add(3);
list.add(2);
list.add(1);
int sum = list.stream().mapToInt(Integer::intValue).sum();
// list.stream() 将集合转换为一个 Stream (流), 这样就能用流式操作来处理集合中的元素
// .mapToInt(Integer::intValue) 将 Stream 转换为 IntStream (整型流), 作用是把 Integer 对象转换为基本类型 int
// Integer::intValue 是方法引用, 相当于 i -> i.intValue()
// .sum() IntStream 的种植操作, 计算流中所有元素的和
System.out.println(sum);
```  

### 2.9 Integer 相比 int 有什么优点
int 是 Java 中的原始数据类型, 而 Integer 是 int 的包装类.
int 和 Integer 的区别: 
    1. 基本类型和引用类型
        int 是一种基本数据类型, 而 Integer 是一种引用类型.
        基本数据类型是 Java 中最基本的数据类型, 它们是预定义的, 不需要实例化就可以使用.
        而引用类型则需要通过实例化对象来使用. 这意味着, 使用 int 来存储一个整数时, 不需要任何额外的内存分配, 而使用 Integer 时, 必须为对象分配内存.
        在性能方面, 基本数据类型的操作通常比相应的引用类型快.
    2. 自动装箱和拆箱
        Integer 作为 int 的包装类, 它可以实现自动装箱和拆箱. 
        自动装箱是指将基本类型转化为相应的包装类类型, 而自动拆箱则是将包装类类型转化为相应的基本类型. 这使得 Java 程序员更加方便地进行数据类型转换. 
            例如, 当我们需要将 int 类型的值赋给 Integer 变量时, Java 可以自动地将 int 类型转换为 Integer 类型.
            同样地, 当我们需要将 Integer 类型的值赋给 int 变量时, Java 可以自动地将 Integer 类型转换为 int 类型.
    3. 空指针异常
        int 变量可以直接赋值为 0, 而 Integer 变量必须通过实例化对象来赋值.
        如果对一个未经初始化的 Integer 变量进行操作, 就会出现空指针异常.
            因为它被赋予了 null 值, 而 null 值是无法进行自动拆箱的.

### 2.10 那为什么还要保留 int 类型?
包装类是引用类型, 对象的引用和对象本身是分开存储的. 而对于基本类型数据, 变量对应的内存块直接存储数据本身.
    因此, 基本类型数据在读写效率方面, 要比包装类高效.
    除此之外, 在 64 位 JVM 上, 在开启引用压缩的情况下, 一个 Integer 对象占用 16 个字节的内存空间, 而一个 int 类型数据只占用 4 字节的内存空间, 前者对空间的占用是后者的 4 倍.
        也就是说, 不管是读写效率, 还是存储效率, 基本类型都比包装类高效.

### 2.11 说一下 Integer 的缓存
Java 的 Integer 类内部实现了一个静态缓存池, 用于存储特定范围内的整数值对应的 Integer 对象.
    默认情况下, 这个范围是 -128 至 127. 当通过 Integer.valueOf(int) 方法创建一个在这个范围内的整数对象时, 并不会每次都生成新的对象实例, 而是复用缓存中的现有对象, 会直接从内存中取出, 不需要新建一个对象.

## 3. 面向对象

### 3.1 怎么理解面向对象? 简单说说封装继承多态.
面向对象是一种编程范式, 它将现实世界中的事物抽象为对象.
    对象具有属性 (称为字段或属性) 和行为 (称为方法). 
    面向对象编程的设计思想是以对象为中心, 通过对象之间的交互来完成程序的功能, 具有灵活性和可扩展性, 通过封装和继承可以更好地应对需求变化.

Java 面向对象的三大特性包括: 封装, 继承, 多态.
    1. 封装
        封装是指将对象的属性 (数据) 和行为 (方法) 结合在一起, 对外隐藏对象的内部细节, 仅通过对象提供的接口与外界交互.
        封装的目的是增强安全性和简化编程, 使得对象更加独立.
    2. 继承
        继承是一种可以使得子类自动共享父类数据结构和方法的机制.
        它是代码复用的重要手段, 通过继承可以建立类与类之间的层次关系, 使得结构更加清晰.
    3. 多态
        多态是指允许不同类的对象对同一消息作出响应. 即同一个接口, 使用不同的实例而执行不同操作.
        多态性可以分为编译时多态 (重载) 和运行时多态 (重写). 它使得程序具有良好的灵活性和扩展性.

### 3.2 多态体现在哪些方面?
1. 方法重载
    方法重载是指同一类中可以有多个同名方法, 它们具有不同的参数列表 (参数类型, 数量或顺序不同). 
    虽然方法名相同, 但根据传入的参数不同, 编译器会在编译时确定调用哪个方法.
        示例: 对于一个 add() 方法, 可以定义为 add(int a, int b) 和 add(double a, double b)

2. 方法重写
    方法重写是指子类能够提供对父类中同名方法的具体实现.
    在运行时, JVM 会根据对象的实际类型确定调用哪个版本的方法. 这是实现多态的主要方式.
        示例: 在一个动物类中, 定义一个 sound 方法, 子类 Dog 可以重写该方法以实现 bark, 而 Cat 可以 Meow.

3. 接口与实现
    多态也体现在接口的使用上, 多个类可以实现同一个接口, 并且用接口类型的引用来调用这些类的方法. 
    这使得程序在面对不同具体实现时保持一贯的调用方式.
        示例: 多个类 (如 Dog, Cat) 都实现了一个 Animal 接口, 当用 Animal 类型的引用来调用 makeSound 方法时, 会触发对应的实现. 

4. 向上转型和向下转型
    在 Java 中, 可以使用父类类型的引用指向子类对象, 这是向上转型. 通过这种方式, 可以在运行时期采用不同的子类实现.
    向下转型是将父类引用转回其子类类型, 但在执行前需要确认引用实际指向的对象类型以避免 ClassCastException.

### 3.3 多态解决了什么问题?
多态是指子类可以替换父类, 在实际的代码运行过程中, 调用子类的方法实现. 
    多态这种特性也需要编程语言提供特殊的语法机制来实现, 比如继承, 接口类.

多态可以提高代码的扩展性和复用性, 是很多设计模式, 设计原则, 编程技巧的代码实现基础.
    比如策略模式, 基于接口而非实现编程, 依赖倒置原则, 里式替换原则, 利用多态去掉冗长的 if-else 语句等等.

### 3.4 面向对象的设计原则你知道有哪些吗?
面向对象编程中的六大原则
    1. 单一职责原则 (SRP)
        一个类应该只有一个引起它变化的原因, 即一个类应该只负责一项职责.
            例子: 考虑一个员工类, 它应该只负责管理员工信息, 而不应负责其他无关工作.
    2. 开放封闭原则 (OCP)
        软件实体应该对扩展开放, 对修改封闭.
            例子: 通过制定接口来实现这一原则, 比如定义一个图形类, 然后让不同类型的图形继承这个类, 而不需要修改图形类本身.
    3. 里氏替换原则 (LSP)
        子类对象应该能够替换掉所有父类对象. 
            例子: 一个正方形是一个矩形, 但如果修改一个矩形的高度和宽度时, 正方形的行为应该如何改变就是一个违反里氏替换原则的例子.
    4. 接口隔离原则 (ISP)
        客户端不应该依赖那些它不需要的接口, 即接口应该小而专.
            例子: 通过接口抽象层来实现底层和高层模块之间的解耦, 比如使用依赖注入.
    5. 依赖倒置原则 (DIP)
        高层模块不应该依赖低层模块, 二者都应该依赖于抽象; 抽象不应该依赖于细节, 细节应该依赖于抽象.
            例子: 如果一个公司类包含部门类, 应该考虑使用合成/聚合关系, 而不是将公司类继承自部门类.
    6. 最少知识原则 (Law of Demeter)
        一个对象应当对其他对象有最少的了解, 只与其直接的朋友交互.

### 3.5 重载和重写有什么区别?
重载是指在同一个类中定义多个同名方法, 而重写是指子类重新定义父类中的方法.
    重载 (Overloading) 指的是在同一个类中, 可以有多个同名方法, 它们具有不同的参数列表 (参数类型, 参数个数或参数顺序不同), 编译器根据调用时的参数类型来决定调用哪个方法.
    重写 (Overriding) 指的是子类可以重新定义父类中的方法, 方法名, 参数列表和返回类型必须与父类中的方法一致, 通过 @Override 注解来明确表示这是对父类方法的重写.

### 3.6 抽象类和普通类区别?
1. 实例化
    普通类可以直接实例化对象, 而抽象类不能被实例化, 只能被继承.
2. 方法实现
    普通类中的方法可以有具体的实现, 而抽象类中的方法可以有实现也可以没有实现.
3. 继承
    一个类可以继承一个普通类, 而且可以继承多个接口; 而一个类只能继承一个抽象类, 但可以同时实现多个接口.
4. 实现限制
    普通类可以被其他类继承和使用, 而抽象类一般用于作为基类, 被其他类继承和扩展使用.

### 3.7 Java 抽象类和接口的区别是什么
1. 两者的特点
    1. 抽象类 (家族继承)
        抽象类用于描述类的共同特性和行为, 可以有成员变量, 构造方法和具体方法. 适用于有明显继承关系的场景.
    2. 接口 (能力证书)
        接口用于定义行为规范, 可以多实现, 只能有常量和抽象方法 (Java 8 以后可以有默认方法和静态方法) 适用于定义类的能力或功能.

2. 两者的区别
    1. 实现方式
        实现接口的关键字为 implements, 继承抽象类的关键字为 extends. 
        一个类可以实现多个接口, 但一个类只能继承一个抽象类. 
        所以, 使用接口可以间接地实现多重继承.
    2. 方法方式
        接口只有定义, 不能有方法的实现, java 1.8 中可以定义 default 方法体
        而抽象类可以有定义与实现, 方法可在抽象类中实现.
    3. 访问修饰符
        接口成员变量默认为 public static final, 必须赋初值, 不能被修改; 其所有的成员方法都是 public, abstract 的.
        抽象类中成员变量默认 default, 可在子类中被重新定义, 也可被重新赋值; 抽象方法被 abstract 修饰, 不能被 private, static, synchronized 和 native 等修饰, 必须以分号结尾, 不带花括号.
    4. 变量
        抽象类可以包含实例变量和静态变量, 而接口只能包含常量 (即静态常量).

### 3.8 抽象类能加 final 修饰吗
不能, Java 中的抽象类是用来被继承的, 而 final 修饰符用于禁止类被继承或方法被重写. 
    因此, 抽象类和 final 修饰符是互斥的, 不能同时使用.

### 3.9 接口里面可以定义哪些方法?
1. 抽象方法
    抽象方法是接口的核心部分, 所有实现接口的类都必须实现这些方法. 抽象方法默认是 public 和 abstract, 这些修饰符可以省略.

```Java
public interface Animal {
    void makeSound();
}
```

2. 默认方法
    默认方法是在 Java 8 中引入的, 允许接口提供具体实现. 实现类可以选择重写默认方法.

```Java
public interface Animal {
    void makeSound();

    default void Sleep() {
        System.out.println("Sleeping...");
    }
}
```

3. 静态方法
    静态方法也是在 Java 8 中引入的, 它们属于接口本身, 可以通过接口名直接调用, 而不需要实现类的对象.

```Java
public interface Animal {
    void makeSound();

    static void staticMethod() {
        System.out.println("Static method in interface.");
    }
}
```

4. 私有方法
    私有方法是在 Java 9 中引入的, 用于在接口中为默认方法或其他私有方法提供辅助功能. 这些方法不能被实现类访问, 只能在接口内部使用.

```Java
public interface Animal {
    void makeSound();

    default void Sleep() {
        System.out.println("Sleeping...");
        logSleep();
    }

    private void logSleep() {
        System.out.println("Logging sleep");
    }
}
```

### 3.10 抽象类可以被示例化吗?
在 Java 中, 抽象类本身不能被实例化.
    这意味着不能使用 new 关键字直接创建一个抽象类的对象. 
    抽象类的存在主要是为了被继承, 它通常包含一个或多个抽象方法 (由 abstract 关键字修饰且无方法体的方法), 这些方法需要在子类中被实现.

抽象类可以有构造器, 这些构造器在子类实例化时会被调用, 以便进行必要的初始化工作.
    然而, 这个过程并不是直接实例化抽象类, 而是创建了子类的实例, 间接地使用了抽象类的构造器.

```Java
public abstract class AbstractClass {
    public AbstractClass() {
        // 构造器代码
    }

    public abstract void abstractMethod() {

    }
}

public class ConcreteClass extends AbstractClass {
    public ConcreteClass() {
        super();  // 调用抽象类的构造器
    }

    @Override
    public void abstractMethod() {
        // 实现抽象方法
    }
}

// 下面的代码可以运行
ConcreteClass obj = new ConcreteClass();
```

在这个例子中, ConcreteClass 继承了 AbstractClass 并实现了抽象方法 abstractMethod(). 
    当我们创建 ConcreteClass 实例时, AbstractClass 的构造器被调用, 但这并不意味着 AbstractClass 被实例化; 实际上我们创建的是一个 ConcreteClass 的一个对象.

简而言之, 抽象类不能直接实例化, 但通过继承抽象类并实现所有抽象方法的子类是可以被实例化的. 

### 3.11 接口可以包含构造函数吗?
在接口中, 不可以有构造方法.
    在接口里写入构造方法时, 编译器提示: Interfaces cannot have constructors, 因为接口不会有自己的实例的, 所以不需要有构造函数.

构造函数就是初始化 class 的属性或者方法, 在 new 的一瞬间自动调用. 
    而 Java 的接口, 都不能 new, 也就自然没有构造函数了.

### 3.12 解释 Java 中的静态变量和静态方法
在 Java 中, 静态变量和静态方法是与类本身关联的, 而不是与类的实例 (对象) 关联. 
    它们在内存中只存在一份, 可以被类的所有实例共享.

1. 静态变量
    静态变量 (也称类变量) 是在类中使用 static 关键字声明的变量. 他们属于类而不是任何具体的对象. 主要特点如下:
        1. 共享性
            所有该类的实例共享同一个静态变量. 如果一个实例修改了静态变量的值, 其他实例也会看到这个更改.
        2. 初始化
            静态变量在类被加载时初始化, 只会对其进行一次分配内存.
        3. 访问方式
            静态变量可以直接通过类名访问, 也可以通过实例访问, 但推荐使用类名.

```Java
public class MyClass {
    static int staticVar = 0; // 静态变量

    public MyClass() {
        staticVar ++; // 每创建一个对象, 静态变量自增. 
    }

    public static void printStaticVar() {
        System.out.println("Static Var: " + staticVar);
    }
}

// 使用示例
MyClass obj1 = new MyClass();
MyClass obj2 = new MyClass();
MyClass.printStaticVar(); // 输出 Static Var : 2
```

2. 静态方法
    静态方法是在类中使用 static 关键字声明的方法. 
    类似于静态变量, 静态方法也属于类, 而不属于任何对象. 主要特点: 
        1. 无实例依赖
            静态方法可以在没有创建类实例的情况下调用. 对于静态方法来说, 不能直接访问非静态的成员变量或方法, 因为静态方法没有上下文的实例.
        2. 访问静态成员
            静态方法可以直接调用其他静态变量和静态方法, 但不能直接访问非静态成员.
        3. 多态性
            静态方法不支持重写 (@Override) 但可以被隐藏 (Hide).

```Java
public class MyClass {
    static int count = 0;
     
    // 静态方法
    public static void incrementCount() {
        count ++;
    }

    public static void displayCount() {
        System.out.println("Count: " + count);
    }
}

// 使用示例
MyClass.incrementCount(); // 调用静态方法
MyClass.displayCount(); // 输出 Count: 1
```

3. 使用场景
    1. 静态变量
        常用于需要在所有对象间共享的数据, 如计数器, 常量等.
    2. 静态方法
        常用于助手方法 (utility methods), 获取类级别的信息或者没有依赖于实例的数据处理.

### 3.13 非静态内部类和静态内部类的区别?
1. 内部类: 类中定义的类. 
2. 非静态内部类依赖于外部类的实例, 而静态内部类不依赖于外部类的实例.
3. 非静态内部类可以访问外部类的实例变量和方法, 而静态内部类只能访问外部类的静态成员.
4. 非静态内部类不能定义静态成员, 而静态内部类可以定义静态成员.
5. 非静态内部类在外部类实例化后才能实例化, 而静态内部类可以独立实例化.
6. 非静态内部类可以访问外部类的私有成员, 而静态内部类不能直接访问外部类的私有成员, 需要通过实例化外部类来访问.

### 3.14 非静态内部类可以直接访问外部方法, 编译器是怎么做到的?
非静态内部类可以直接访问外部方法是因为编译器在生成字节码时会为非静态内部类维护一个**指向外部类实例的引用**. 
    这个引用使得非静态内部类能够访问外部类的实例变量和方法. 
    编译器会在生成非静态内部类的构造方法时, 将外部类实例作为参数传入, 并在内部类的实例化过程中建立外部类实例与内部类实例之间的联系, 从而实现直接访问外部方法的功能.

## 4. 关键字

### 4.1 Java 中 final 作用是什么?
final 关键字主要有以下三个方面的作用: 用于修饰类, 方法和变量. 
    1. 修饰类
        当 final 修饰一个类时, 表示这个类不能被继承, 是类继承体系中的最终形态. 
        例如, Java 中的 String 类就是用 final 修饰的, 这保证了 String 类的不可变性和安全性, 防止其他类通过继承来改变 String 类的行为和特性. 
    2. 修饰方法
        当 final 修饰基本数据类型的变量时, 该变量一旦被赋值就不能再改变.
            例如, final int num = 0; 这里的 num 就是一个常量, 不能再对其进行重新赋值操作, 否则就会导致编译错误.     
        对于引用数据类型, final 修饰意味着这个引用变量不能再指向其他对象, 但是对象本身的内容还是可以改变的. 
            例如, final StringBuilder sb = new StringBuilder("Hello");
            就不能让 sb 再指向其他的 StringBuilder 对象, 但是可以通过 sb.append(" World"); 来修改字符串的内容. 

### 4.2 Java 中 static 的作用是什么?
static 关键字主要用于修饰类的成员 (变量, 方法, 代码块) 和内部类. 核心作用是**将成员与类本身关联, 而非与类的示例 (对象) 关联**. 具体作用如下:

#### 4.2.1 修饰变量
    被 static 修饰的变量属于类本身, 而非类的某个实例. 所有对象共享同一份静态变量, 内存中只存在一份副本. 
    可以通过 `类名.变量名` 直接访问, 无需创建对象 (也可以通过对象访问, 但是不推荐)
    通常用于存储所有对象共享的数据, 如常量, 计数器等.  

```Java
public class Student {
    // 静态变量 (所有学生共享一个学校名称)
    public static String schoolName = "阳关中学";
    // 实例变量 (每个学生有自己的姓名)
    private String name;
}

// 访问静态变量
public class Test {
    public static void main(String[] args) {
        System.out.println(Student.schoolName); // 直接通过类名访问
    }
}
```

#### 4.2.2 修饰方法
    静态方法属于类, 不属于任何实例, 因此**不能直接访问类中的非静态成员 (变量 / 方法)** (因为非静态成员依赖于对象存在), 但可以访问静态成员. 
    通过 `类名.方法名` 直接调用, 无需创建对象. 
    通常用于工具类方法 (如 Math.random()), 工厂方法等, 不需要依赖对象状态即可完成操作.  

```Java
public class MathUtils {
    // 静态方法 (无需创建对象即可调用)
    public static int add(int a, int b) {
        return a + b;
    }
}

// 调用静态方法
public class Test {
    public static void main(String[] args) {
        int result = MathUtils.add(1, 2); // 直接通过类名调用
    }
}
```

#### 4.2.3 修饰代码块
静态代码块在**类加载时执行**, 且只执行一次 (优于对象构造方法), 用于**初始化静态变量**或执行**类级别的预处理操作**.
多个静态代码块按定义顺序执行, 且先于非静态代码块和构造方法.

```Java
public class Database {
    private static String url;

    // 静态代码块, 初始化静态变量
    static {
        url =  "jdbc:mysql://localhost:3306/test";
        System.out.println("数据库连接地址初始化完成");
    }
}
```

#### 4.2.4 修饰内部类
静态内部类不依赖于外部类的实例, 可以独立存在. **不能直接访问外部类的非静态成员** (需通过外部类实例访问).
    当内部类与外部类的实例无关时使用, 避免内部类持有外部类的引用导致的内存泄露. 

```Java
public class OuterClass {
    private static int staticVar = 10;
    private int instanceVar = 20;

    // 静态内部类
    public static class StaticInnerClass {
        public void print() {
            System.out.println(staticVar); // 可以访问外部类的静态变量
            // System.out.println(instanceVar); // 错误, 不能访问非静态变量
        }
    }
}

// 使用静态内部类
public class Test {
    public static void main(String[] args) {
        OuterClass.StaticInnerClass inner = new OuterClass.StaticInnerClass();
        inner.print(); 
    }
}
```

## 5. 深拷贝和浅拷贝

### 5.1 深拷贝和浅拷贝的区别?
1. 浅拷贝是指只复制对象本身和其内部的值类型字段, 但不会复制对象内部的引用类型字段.
    换句话说, 浅拷贝只是创建一个新的对象, 然后将原对象的字段值复制到新对象中, 但如果原对象内部有引用类型的字段, 只是将引用复制到新对象中, 两个对象指向的是同一个引用对象.

2. 深拷贝是指在复制对象的同时, 将对象内部的所有引用类型字段的内容也复制一份, 而不是共享引用.
    换句话说, 深拷贝会递归复制对象内部所有引用类型的字段, 生成一个全新的对象以及其内部的所有对象.

#### 5.2 实现深拷贝的三种方法是什么?
1. 实现 Cloneable 接口并重写 clone() 方法
    这种方法要求**对象及其所有引用类型字段**都实现 Cloneable 接口, 并且重写 clone() 方法.
    在 clone() 方法中, 通过递归克隆引用类型字段来实现深拷贝.

```Java
class MyClass implements Cloneable { 
    // Cloneable 是一个标记接口 (没有方法), 告诉 JVM 这个类的对象可以调用 clone() 方法
    // 如果不实现这个接口, 调用 clone() 就会抛出 CloneNotSupportException
    private String field1; // String 是不可变对象
    private NestedClass nestedObject; // 引用类型的嵌套对象

    @Override
    protected Object clone() throws CloneNotSupportedException { 
        // protected 关键字能在本类, 同包, 子类(不同包) 使用
        // 步骤1: 调用父类 (Object 类) 的 clone() 进行浅拷贝
        MyClass cloned = (MyClass) super.clone(); 
        // 步骤2：手动深拷贝引用对象
        cloned.nestedObject = (NestedClass) nestedObject.clone(); 
        return cloned;
    }
}

class NestedClass implements Cloneable {
    private int nestedField;
    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

2. 使用序列化和反序列化
    通过将对象序列化为字节流, 再从字节流反序列化为对象来实现深拷贝. 要求对象及其所有引用类型字段都实现 Serializable 接口.

```Java
import java.io.*;
class MyClass implements Serializable {
    private String field1;
    private NestedClass nestedObject;

    public MyClass deepCopy() {
        try {
            ByteArrayOutputStream bos = new ByteArrayOutputStream();
            ObjectOutputStream oos = new ObjectOutputStream(bos);
            oos.writeObject(this);
            oos.flush();
            oos.close();

            ByteArrayInputStream bis = new ByteArrayInputStream(bos.toByteArray());
            ObjectInputStream ois = new ObjectInputStream(bis);
            return (MyClass) ois.readObject();
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
            return null;
        }   
    }
}

class NestedClass implements Serializable {
    private int nestedField;
}
```

3. 手动递归复制
    针对特定对象结构, 手动递归复制对象及其引用类型字段. 适用于对象结构复杂度不高的情况.

```Java
class MyClass {
    private String field1;
    private NestedClass nestedobject;
    
    public MyClass deepcopy() {
        MyClass copy = new MyClass();
        copy.setField1(this.field1);
        copy.setNestedobject(this.nestedobject.deepCopy());
        return copy;
    }
    
    public void setField1(String field1) {
        this.field1 = field1;
    }
    
    public void setNestedobject(NestedClass nestedobject) {
        this.nestedobject = nestedobject;
    }
}

class NestedClass {
    private int nestedField;
    
    public NestedClass deepCopy() {
        NestedClass copy = new NestedClass();
        copy.setNestedField(this.nestedField);
        return copy;
    }
    
    public void setNestedField(int nestedField) {
        this.nestedField = nestedField;
    }
}
```

## 6. 泛型

### 6.1 什么是泛型?
泛型是 Java 编程语言中的一个重要特性, 它允许类, 接口和方法在定义时使用一个或多个类型参数, 这些类型参数在使用时可以被指定为具体的类型.
泛型的主要目的是在编译时提供更强的类型检查, 并且在编译后能够保留类型信息, 避免了在运行时出现类型转换异常.

### 6.2 为什么需要泛型? 
1. 适用于多种数据类型执行相同的代码

```Java
public static int add(int a, int b) {
    System.out.println(a + " + " + b + "=" + (a + b));
    return a + b;
}

public static float add(float a, float b) {
    System.out.println(a + " + " + b + "=" + (a + b));
    return a + b;
}

public static double add(double a, double b) {
    System.out.println(a + " + " + b + "=" + (a + b));
    return a + b;
}
```

如果没有泛型, 要实现不同类型的加法, 每种类型都需要重载一个 add 方法; 而通过泛型, 可以复用为一个方法:
```Java
public static <T extends Number> add(T a, T b) {
    System.out.println(a + " + " + b + "=" + (a.doubleValue() + b.doubleValue()));
    return a.doubleValue() + b.doubleValue();
}
```










































































































































































































































































