---
title: Java基础
date: 2022-03-27 20:23:24
tags: Java
---

JAVA基础

第1章 JAVA语言概述

第2章 基本语法

第3章 数组

## 第4/5/6章 面向对象

1. 类和类的成员：属性、方法、构造器、代码块和内部类
2. 封装、继承和多态
3. 关键字及其使用

### Day 8 （P198-P218）

#### 1、形参与实参

形参：方法定义时，声明的小括号内的参数

实参：方法调用时，实际传递给形参的数据

#### 2、值传递机制

方法的形参传递机制：值传递

如果参数是基本数据类型，此时实参赋给形参的是实参真实存储的数据值

如果参数是引用数据类型，此时实参赋给形参的是实参存储数据的地址值

#### 3、属性（成员变量）vs 局部变量

相同点：

​	1、定义变量的格式：数据类型 变量名=变量值

​	2、先声明后使用

​	3、变量都有其作用域

不同点：

​	1、在类中声明的位置不同，属性直接定义在类的{}内，局部变量声明在方法内，方法形参，代码块内，构造器     	形参、构造器内部的变量

​	2、权限修饰符：

​		属性：可以在声明属性时，指明其权限，使用权限修饰符

​		常用的权限修饰符：private、public、缺省、protected

​		局部变量：不可以使用权限修饰符

​	3、默认初始化值

​		属性：类的属性，根据其类型都有默认初始化值

​					整型（byte、short、int、long）:0

​					浮点型（float、double）:0.0

​					字符型（char）:0（或'\u0000'）

​					布尔型（boolean）:false

​					引用数据类型（**字符串**、类、数组、接口）:null

​		局部变量：没有默认初始化，在调用局部变量之前一定要显式化赋值

​					特别的，形参在调用时赋值即可

​	4、在内存中加载的位置

​		属性：加载到堆空间中

​		局部变量：加载到栈空间

![](C:\Users\86187\Desktop\MD笔记\JAVA基础\变量.png)

### Day 9 （P219-P241）

#### 1、封装与隐藏

高内聚：类的内部数据操作细节自己完成，不允许外部干涉

低耦合：仅对外暴露少量的方法用于使用

#### 2、权限修饰符

​	1、四种权限（从小到大）：private，缺省(default)，protected，public

| 修饰符    | 类内部 | 同一个包 | 不同包的子类 | 同一个工程 |
| --------- | ------ | -------- | ------------ | ---------- |
| private   | Yes    |          |              |            |
| 缺省      | Yes    | Yes      |              |            |
| protected | Yes    | Yes      | Yes          |            |
| public    | Yes    | Yes      | Yes          | Yes        |

​	2、4种权限可以用来修饰类及内部类的内部结构：属性、方法、构造器、内部类

​		  修饰类只能用缺省、public

​		  总结封装性：JAVA提供了4种权限修饰符来修饰类及类的内部结构，体现类及类的内部结构在被调用时的可见性的大小

#### 3、构造器

​	1、构造器的作用：创建对象、初始化对象的属性

​		  如果没有显式的定义类的构造器，则系统默认提供一个空参的构造器

​		  一个类中定义的多个构造器彼此构成重载

​	2、属性赋值的选后顺序：①默认初始化 ②显式初始化 ③构造器中赋值 ④通过对象.方法或对象.属性赋值

​	3、只要造对象，就一定会使用构造器，这句话任何时候都是对的

#### 4、UML类图![image-20211112145641093](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211112145641093.png)

#### 5、this关键字

​	1、方法的形参和类的属性同名时，必须显式使用this.变量的方式，表明此变量是属性，而非形参

​	2、this可以调用属性、方法和构造器

​	3、可以显式使用"this(形参列表)"方式，调用本类中指定的其他构造器

​		  "this(形参列表)"必须声明在当前构造器的首行

​		  构造器中不能使用 "this(形参列表)"的方式调用自己

​		  构造器内部最多只能声明一个"this(形参列表)"调用其他构造器

#### 6、package关键字的使用

​	1、使用package声明类或者接口所属的包，声明在源文件的首行

​	2、每“.”一次，就代表一层文件目录

​	3、同一个包下，不能命名同名的接口和类，不同包下可以声明同名的接口和类

#### 7、MVC设计模式

将程序分成三个层次：视图模型层（view）、控制器层（controller）与数据模型层（model）![image-20211112170536925](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211112170536925.png)

#### 8、import关键字

​	1、在源文件中使用import导入指定包下的类和接口

​	2、如果使用的类或者接口时java.lang包下定义的，则可以省略import结构

​		  如果使用的类或者接口是本包下定义的，则可以省略import结构

​	3、如果在源文件中使用了不同包下的同名类，则必须至少有一个类需要以全类名的方式显示

​	4、使用“xxx.*”的方式可以调用包中的所有结构，但如果是子包，仍需要显式调用（我的理解就是没有子包，都是并列的包）

​	5、import static：导入类或接口中的静态结构（意思就是导入属性或者方法），单import是导入类或接口

### Day 10 (P242-P264)

#### 1、项目2

​		1、动态数组，大小随时改变的写法   

​		2、删除数组中的元素，后面的元素要覆盖前面的，不能直接指空

#### 2、继承性

1、继承性的优点：

​	①减少代码冗余，提高代码复用性

​	②便于功能的扩展

2、继承的格式：classA extends classB{}

​	A：子类、派生类、subclass

​	B：父类、基类、超类、superclass

​	体现：一旦子类继承父类之后，子类就获取了父类中声明的属性和方法。

​	特别的，父类中声明为private的属性或者方法，仍然认为获取了父类中私有的结构，只是因为封装性的影响，子类不能直接调用。子类继承父类之后，可以声明自己持有的属性或方法实现功能的扩展。

3、JAVA中关于继承的规定	

​	①支持单继承和多层继承，不允许多重继承

​		一个子类只能有一个父类，一个父类可以派生多个子类

​	②直接父类和间接父类

​	③所有类都直接或间接继承于Object类

### Day 11 （P265-P284）

#### 1、方法重写（overwrite）

​	1、重写：子类继承父类以后，可以对父类中同名参数的方法进行覆盖操作

​	2、重写之后，当创建子类对象以后，通过子类对象调用子父类中的同名同参数的方法时，实际执行的是子类重写父类的方法

​	3、重写的规定：

​		方法的声明：权限修饰符 返回值类型 方法名（形参列表）throws 异常的类型{ 方法体 }

​		子类中叫**重写**的方法，父类中叫**被重写**的方法

​		①子类重写的方法的方法名和形参列表与父类被重写的方法名和形参列表相同

​		②子类重写的方法的权限修饰符不小于父类被重写方法的权限修饰符

​			特殊情况：子类不能重写父类中声明为private权限的方法

​		③返回值类型：

​			父类被重写的方法的返回值是void：子类重写的方法只能是void

​			父类被重写的方法的返回值是引用类型：子类重写的方法只能和父类相同或者为其子类

​			父类被重写的方法的返回值是基本类型：子类重写的方法只能是相同的基本类型

​		④子类重写的方法抛出的异常类型不大于父类被重写的方法抛出的异常类型

​		⑤必须是非static		

#### 2、super关键字

​	1、super可以用来调用属性、方法和构造器。

​	2、当子类和父类中定义了同名的属性时，要想在子类中调用父类中声明的属性则必须显式使用super.属性。

​		  当子类重写了父类中的方法之后，要在子类中调用父类中被重写的方法则必须显式使用super.属性。

​	3、super调用构造器

​		  可以在子类中使用 super（形参列表）的方式调用父类中声明的指定的构造器，必须声明在首行

​		  在类的构造器中 this( 形参列表 )和super（形参列表）只能二选一，在构造器没有显式声明时，默认调用父类中的空参构造器

#### 3、多态性

​	1、父类的引用指向子类的对象——对象的多态性

​	2、多态的使用：虚拟方法的调用

​		  有了对象的多态性之后，在编译期只能调用父类中声明的方法，编译期实际执行的是子类重写父类的方法

​		  **编译看左边，运行看右边**

​	3、多态性使用前提：①有类的继承关系 ②要有方法的重写

​	4、对象的多态性只适用于方法不适用于属性（还是父类的属性）

​	5、多态性是一个运行时行为，要到运行的时候才知道具体是哪一个，而重载是编译时行为，编译的时候就知道具体是哪一个

### Day 12 （P285-P311）

#### 1、向下转型

​	1、有了对象的多态性之后，内存中实际上是加载了子类特有的属性和方法的，但是由于变量声明为父类类型，导致编译时只能使用父类中声明的属性和方法。使用强制类型转换符之后就可以使用子类的属性和方法，即向下转型。

​	2、自动类型提升和强制类型转化（有可能会转不成功

​	3、P289：向下转型的几个问题

​	(那几个练习还蛮重要的感觉)

#### 2、instanceof关键字

​	1、a instanceof A:判断对象a是否为A的实例，如果是返回true。

​	2、使用情景：避免在向下转型时出现异常，先进行判断。

#### 3、Object类

​	1、Object类是所有类的根父类，类中的属性和方法具有通用性，Object类中只声明了一个空参构造器

​	2、Object类中的方法：

- clone()，克隆一个对象
- funalize()，对象调用的用于垃圾回收的方法（不要主动调用，由垃圾回收器调用）
- **equals()** / **toString()** / getClass() / hashCode() / wait() / notify() / notifyAll()
- 数组也作为Object类的子类出现，可以调用Object类中声明的方法

#### 4、==

​	1、可以使用在基本数据类型变量和引用数据类型变量中

​	2、基本数据类型变量：比较保存的数据（类型可以不同）

​		  引用数据类型变量：比较地址值，即两个引用是否指向同一个对象实体

​	3、基本数据类型除了boolean以外都会有自动类型提升所以不用太关注类型，关注值。引用类型的话类型都不同地址必不可能相同

#### 5、equals（）

​	1、基本数据类型不是类，无法调用equals（）方法，只适用于引用数据类型

​	2、Object类中equals()方法的定义：

```java
public boolean equals(Object obj){
    return (this==obj);
}
```

​	说明Object类中equals()方法和==相同，比较地址值，即两个引用是否指向同一个对象实体

​	3、String\Date\File\包装类都重写了Object类中的equals()方法，重写后比较的是属性是否相同（内容是否相同）

​	4、自定义的类如果使用equals()方法，也通常是比较实体内容，那就需要重写。重写的步骤：先==判断一下，如果==直接返回true，然后判断是否为同一类型，是的话向下转型然后比较需要的属性

​		  系统可以自动生成equals()方法比较你需要的属性。

​	5、x.equals(null)永远都是false,比较的前提是类型相同

​	6、常量池

```java
String s1="BB";
String s2="BB";
System.out.println(s1==s2);//true
```

两个对象都在常量池中，两个对象的地址一样

当 "=="运算符的两个操作数都是 包装器类型的引用，则是比较指向的是否是同一个对象，而如果其中有一个操作数是表达式（即包含算术运算）则比较的是数值（即会触发自动拆箱的过程）。另外，对于包装器类型，equals方法并不会进行类型转换。

#### 6、toString()

​	1、当我们输出一个对象的引用时，实际上是调用当前对象的toString()

​	2、Object类中toString()的定义

```java
public String toString(){
    return getClass().getName()+"@"+Integer.toHexString(hashCode());
}
```

输出：类名@地址值（JVM中的虚拟地址值）

​	3、String/Date/File/包装类把toString()重写了，输出的是内容。自定义类也可以重写。

#### 7、单元测试

（讲的是Eclipse的单元测试，要用的话就去找IDEA的）

#### 8、包装类的使用

| 基本数据类型 | 包装类    |
| ------------ | --------- |
| byte         | Byte      |
| short        | Short     |
| int          | Integer   |
| long         | Long      |
| float        | Float     |
| double       | Double    |
| boolean      | Boolean   |
| char         | Character |

1、基本类型与包装类的转换

- 基本数据类型-->包装类：调用包装类的构造器
- 包装类-->基本数据类型：调用xxxValue()  

2、JDK 5.0新特性：自动装箱和自动拆箱

```java
int num=10;
Integer num1=num;//自动装箱：基本数据类型--->包装类
int num2=num1;//自动拆箱：包装类--->基本数据类型  
```

3、基本数据类型、包装类--->String

```java
//方式1:连接运算（其他基本类型都可以用这种方式）
int num=10;
String str=num+"";
//方式2：valueOf()
float f1=12.3f;
String str1=String.valueOf(f1);
```

4、String--->基本数据类型、包装类：调用包装类的parseXxx()

```java
String str="123";
int num=Integer.parseInt(str);
```

可能会报NumberFormatException，比如"true"要转int就是不可能的，就会报错![image-20211119210908171](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211119210908171.png)

熟练掌握：**自动装箱和拆箱，valueOf()，parseXxx()**

5、课后题

```java
//题目1
Object o1=true?new Integer(1):new Double(2.1);
System.out.println(o1);//1.0
//三目运算符要求类型相同，int自动类型提升为double
Object o2;
if(true)o2=new Integer(1);
else o2=new Double(2.0);
System.out.println(o2);//1
```

```java
//题目2
public void method(){
    Integer i=new Integer(1);
    Integer j=new Integer(1);
    System.out.println(i == j);//false
    
    Integer m=1;
    Integer n=1;
    System.out.println(m == n);//true
    
    Integer x=128;
    Integer y=128;
    System.out.println(x == y);//false
}
```

①两个不同的对象

②Integer内部定义了IngeterCache()方法，其中定义了Ingeter[]，保存了-128~127的整数，如果给Ingeter赋值的范围在-128~127以内，可以直接使用数组中的元素，不用去new了，如此可以提高效率

③超过了缓存池的大小，所以是new了两个不同的对象

### Day 13 (P312-P338)

#### 1、static关键字

​	1、static可以用来修饰：属性、方法、代码块、内部类

​	2、static修饰属性：静态变量（类变量），非静态变量（实例变量)

- 按是否有static修饰，属性又可分为静态属性和非静态属性

- 实例变量：创建了多个对象之后，每个对象独立拥有一套非静态属性，修改其中一个对象的非静态属性不会导致其他对象中同样的属性的修改

- 静态变量：多个对象共享同一个静态变量，当通过某一个对象修改静态变量时，其他对象的该变量也一起改变

- 静态变量随着类的加载而加载，早于对象的创建，可以通过“类.静态变量”的方式调用

  由于类只会加载一次，静态变量在内存中也只有一份

- 静态属性举例：System.out，Math.PI

​	3、static修饰方法：静态方法

​		  ① 静态方法随着类的加载而加载，早于对象的创建，可以通过“类.静态方法”的方式调用

​		  ② 静态方法中，只能调用静态的方法和属性

​			   非静态方法中，既可以调用静态的属性和方法，也可以调用非静态的

​	4、在静态方法内，不能室友this、super关键字

​	5、在开发中，如何确定一个属性要声明为static？

​		  属性可以被多个对象共享，不会因为对象的不同而不同

​	6、在开发中，如何确定一个方法要声明为static？

​		 工具类中的方法，习惯上声明为static，比如Math\Arrays\Collections

​		 操作静态属性的方法

​	7、使用举例

​		 ①Math\Arrays\Collections等工具类

​		 ②单例模式

#### 2、内存结构图

栈：局部变量

堆：new出来的结构，对象、数组

方法区：类的加载信息、静态域、常量池

```Java
class Chinese{
    String name;
    int age;
    static String nation;
}
public static void main(String[] args){
    Chinese.nation="中国";
    
    Chinese c1=new Chinese();
    c1.name="姚明";
    c1.age=40;
    
    Chinese c2=new Chinese();
    c1.name="马龙";
    c1.age=30;
    
    System.out.println(c1.nation);//中国
    c1.nation="CHN";
    System.out.println(c2.nation);//CHN
    c2.nation="CHINA";
    System.out.println(c1.nation);//CHINA
}
```

![](C:\Users\86187\Desktop\MD笔记\JAVA基础\图片1.png)

#### 3、单例设计模式

1. 单例设计模式就是采取一定的方法保证整个的软件系统中，对某个类只能存在一个对象实例，并且该类只提供一个取得其对象实例的方法。

2. 单例模式的优点：只生成一个实例，减少系统性能开销。使用例：getRuntime()

3. 区分饿汉式和懒汉式：

   饿汉式——缺点：先创建对象，对象加载时间过长；优点：线程安全

   懒汉式——优点：延迟对象的创建；缺点：下述写法线程不安全

   **面试让你写的话优先写饿汉式**

4. ```Java
   public class SingletonTest{
       public static void main(String[] args){
           
           Bank bank1=Bank.getInstance();
           Bank bank2=Bank.getInstance();
           System.out.println(bank1==bank2);//true
           
           
       }
   }
   //--------饿汉式单例模式
   //为什么要用静态呢，要在外面调用getInstance()方法，如果没有static，就得先造一个Bank类的对象，但类的构造器是私有化的，造不了对象，想要直接调用类的方法，必须声明static，静态的方法中才能调用静态的属性，所以对象也必须是静态的
   class Bank{
       //1、私有化类的构造器
       private Bank(){
           
       }
       //2、内部创建类的对象
       private static Bank instance=new Bank();
       //3、提供公共的静态方法返回类的对象,可以在main方法中通过类名调用方法
       public static Bank getInstance(){
           return instance;
       }
   }
   //--------懒汉式单例模式
   class Order{
       //1、私有化类的构造器
       private Order(){
           
       }
       //2、声明当前类的对象
       private static Order instance=null;
       //3、声明public、static的返回当前类的对象
       public static Order getInstance(){
           if(instance==null){
               instance=new Order();
           }
           return instance;
       }
   }
   ```

#### 4、理解main方法

1. main()方法是程序的入口
2. main()方法也是一个普通的静态方法
3. main()方法可以作为我们与控制台交互的方式

#### 5、代码块

```java
class Person{
    //属性
    String name;
    int age;
    static String desc="我是一个人";
    //构造器
    public Person(){
        
    }
    public Person(String name,int age){
        this.name=name;
        this.age=age;
    }
    //非静态代码块
    {
        System.out.println("block")
    }
    //静态代码块
    static{
        System.out.println("static block")
    }
    //方法
    public void eat(){
        System.out.println("吃饭")
    }
    @Override
    public String toString(){
        return "Person[name="+name+",age="+age+"]";
    }        
}
```

1. 代码块用于初始化类和对象，如果有修饰的话只能用static，加上static为静态代码块，不加为非静态

2. 静态代码块：

   ①内部可以有输出语句

   ②随着类的加载而执行，而且只执行一次

   ③如果一个类中使用了多个静态代码块，则按照声明的先后顺序执行

   ④静态代码块的执行优先于非静态代码块的执行

   ⑤只能调用静态的属性或方法

3. 非静态代码块

   ①内部可以有输出语句

   ②随着对象的创建而执行，每创建一个对象就执行一次，可以在创建对象时对对象的属性进行初始化

   ③如果一个类中使用了多个非静态代码块，则按照声明的先后顺序执行

   ④可以调用静态和非静态的属性或方法

4. 给属性赋值的顺序

   ①默认初始化

   ②显式初始化/在代码块中赋值（看谁写在前面）

   ③构造器中初始化

   ④创建对象，通过对象.属性或者对象.方法赋值

5. 代码块的练习值得看一看：P332

#### 6、final关键字

1. final修饰类：此类不能被其他类所继承，比如：String、System、StringBuffer

2. final修饰方法：此方法不能再被重写，比如：Object类中的getClass()

3. static final用来修饰属性：全局常量

4. final修饰变量：此时的变量就称为是一个常量

   final修饰属性：可以考虑赋值的位置：显式初始化，代码块中初始化、构造器中初始化

   final修饰局部变量：尤其是用final修饰形参时，表明此形参是一个常量，当调用此方法时，给常量形参赋实参，一旦赋值就只能在方法体内使用此形参，但不能重新赋值

### Day 14（P339-P366）

P340后面改单例模式的权限修饰符，private改public有必要听一下

#### 1、abstract

##### abstract介绍

1. 可以用于修饰：类（抽象类）、方法（抽象方法）

2. abstract修饰类：

   ①此类不能实例化（也就是不能创建这个类的对象

   ②虽然自己不能实例化，但是子类会调用父类的构造器，所以抽象类中一定有构造器

3. abstract修饰方法

   ① 抽象方法只有方法的声明没有方法体，所在的类一定是抽象类。因为如果类不是抽象的，那这个类就可以造对象，可以造对象就可以调用。反之抽象类中可以没有抽象方法。

   ② 若子类重写了子类重写了父类所有的抽象方法才能实例化，如果没有全部重写，那么子类也是抽象类，也需要用abstract修饰

   ③ abstract不能用来修饰私有方法、静态方法、final关键字修饰的方法、final关键字修饰的类

   因为如果两个方法都是static，不认为两个方法是重写或者覆盖，所以abstract用来修饰静态方法，就无法重写

##### 抽象的应用

模板方法设计模式。在软件开发中实现一个算法时，整体步骤很固定、通用，这些步骤在父类中写好，某些易变的和不确定的部分可以抽象出来给子类实现。

##### 抽象类的匿名子类对象

```java
public static void main(String[] args){
    //匿名对象
    eat(new son());
    //非匿名类的非匿名对象
    son John=new son();
    eat(John);
    //匿名子类对象
    father f=new father(){
        @Override
        public void work() {

        }
        @Override
        public void info(father i) {

        }
    };
}
//普通方法
public static void eat(father f){
    System.out.println("吃饭");
}
//父类
public abstract static class father{
    String name;
    int age;
    public abstract void work();//抽象方法不能有方法体
    public abstract void info(father i);
}
//子类
public class son extends father{//继承
    String name;
    int age;
    @Override
    public void work(){
        System.out.println("上学");
    }
    @Override
    public void info(father i) {
        System.out.println("name:"+i.name+" age:"+i.age);
    }
}
```

#### 2、接口

##### 接口介绍

1. 接口使用Interface来定义，和类是并列关系

2. 接口的定义以及接口中的成员：

   JDK7及以前：只能定义全局常量和抽象方法

   - 全局常量：都是用public static final定义的，可以省略不写
   - 抽象方法：public abstract

   JDK8：除了全局常量和抽象方法，还可以定义静态方法和默认方法

3. 接口中不能定义构造器，意味着接口不可以实例化，通过类去实现（implements）接口。

   如果类覆盖了接口中所有的抽象方法，则可以创造实例；

   如果类没有覆盖接口中所有的抽象方法，则该类仍为抽象类。

4. Java类可以实现多个接口——弥补了单继承性的缺陷

   class AA extends BB implements CC,DD,EE

5. 接口和接口之间可以继承，且可以多继承。接口的使用体现了多态性。

6. 接口是一种规范，面向接口编程。

7. 面试题：抽象类和接口有哪些异同？

##### 接口应用

- 代理模式

代理设计就是为其他对象提供一张代理以控制对这个对象的访问

应用场景：安全代理、远程代理、延迟加载

分类：静态代理、动态代理

- 工厂模式

实现创建者和调用者的分离

##### 接口笔试题

1. 排错

   ```java
   interface A{
       int x=0;
   }
   class B{
       int x=1;
   }
   class C extends B implements A{
       public void pX(){
           System.out.println(x);
       }
       public static void main(String[] args){
           new C().pX();
       }
   }
   ```

   问题：编译期不知道是要输出哪个x

   ```java
   System.out.println(super.x);//这个调用的是父类中的
   System.out.println(A.x);//这个调用的是接口中的
   ```

2. 排错

   ```java
   interface Playable{
       void play();
   }
   interface Bounceable{
       void play();
   }
   interface Rollable extends Playable,Bounceable{
       Ball ball=new Ball("PingPong");
   }
   class Ball implements Rollable{
       private String name;
       public String getName(){
           return name;
       }
       public Ball(String name){
           this.name=name;
       }
       public void play(){
           ball=new Ball("Football");
           System.out.println(ball.getName());
       }
   }
   ```

   - Ball中的play()方法重写可以认为同时重写了Playable和Bounceable的play方法
   - Ball ball是public final的，不能再修改，所以ball=new Ball("Football")是错误的

##### java8中接口新特性

JDK8：除了全局常量和抽象方法，还可以定义静态方法和默认方法（default关键字修饰）

1. 接口中定义的静态方法只能通过接口来调用，接口.方法。
2. 通过实现类的对象，可以调用接口中的默认方法，对象.方法。如果实现类重写了接口中的默认方法，调用时仍然调用的是重写以后的方法
3. 如果子类（或实现类）继承的父类和实现的接口中声明了同名同参数的方法，子类在没有重写此方法的情况下调用的是父类中的方法——类优先原则
4. 如果实现类实现了多个接口，而这个多个接口中定义了同名同参数的默认方法，在实现类没有重写方法的情况下会报”接口冲突“错误，此时需要重写。
5. 如何在子类（或者实现类）调用父类、接口中被重写的方法，接口.super.方法

##### 抽象类和接口的异同

相同点：不能实例化，都可以包含抽象方法

不同点：

1. 把抽象类和接口（java7、java8)的定义、内部结构解释说明
2. 类：单继承性，接口：多继承性

#### 3、内部类

1. Java允许将一个类A声明在另一个类B中，A为内部类，B为外部类

2. 内部类的分类：成员内部类、局部内部类（方法内，代码块内，构造器内）

3. 成员内部类

   - 作为外部类的成员：可以调用外部类的结构，可以被static修饰
   - 作为一个类：可以定义属性、方法、构造器，可以用final、abstract修饰，可以被继承 

4. 需要关注的问题：

   - 如何实例化成员内部类的对象：外部类Person，静态内部类Brain，非静态内部类Lungs

     静态成员内部类：new 外部类.内部类()

     ```java
     Person.Brain brain=new Person.Brain();
     ```

     非静态成员内部类：先造对象，对象.new 内部类()

     ```java
     Person p=new Person();
     p.Lungs lungs=p.new Lungs();
     ```

   - 如何在成员内部类中区分调用外部类的结构

     形参直接调，所在类的用this.结构，外部类的用外部类.this.结构

   - 成员内部类和局部内部类在编译以后都会生成字节码文件

     成员内部类：外部类$内部类名.class

     局部内部类：外部类$数字 内部类名.class

   - 在局部内部类的方法中，如果调用局部内部类所在的方法中的局部变量，该局部变量必须用final关键字修饰(JAVA8之后可以不写出来，但仍然还是final的)

   ```java
   public void Person(){
       int num=10;
       class AA{//局部内部类
           public void show(){//局部内部类的方法
               num=20;//试图修改会报错
               System.out.println(num);//调用局部内部类所在的方法中的局部变量
           }
       }
   }
   ```

   - 开发中局部内部类的使用

     常用的局部内部类：

     ```java
     //方式一
     public Comparable getCompareble(){
         class MyComparable implements Comparable{//局部内部类
             @Override
             public int compareTo(Object o){
                 return 0;
             }
         }
         return new MyComparable();
     }
     //方式二
     public Comparable getCompareble(){
         return new Comparable(){
             @Override
             public int CompareTo(Object o){
                 return 0;
             }
         };
     }
     ```





#### 4、关键字总结

static可以用来修饰：属性、方法、代码块、内部类

final关键字可以用来修饰：类、方法、变量（属性和局部变量）

abstract可以用于修饰：类、方法

## 第7章 异常处理

### Day 15（P367-P385） 

#### 1、异常概述与异常体系结构

JAVA.lang.Throwable：

1. Error：JAVA虚拟机无法解决的严重问题
2. Exception：其他因变成错误或偶然的外在因素导致的一般性问题

- 编译时异常
  - IOException
  - ClassNotFoundException
- 运行时异常
  - NullPointerException
  - ArrayIndexOutOfBoundsException

面试题

1. 常见的异常有哪些？举例说明

2. final/finally/finalize

3. throw/throws

   throw：抛出一个异常类的对象，生成异常对象的过程，声明在方法体内

   throws：属于异常处理的方式，声明在方法体处

4. String / StringBuffer / StringBuilder

5. ArrayList / LinkedList

6. HashMap / LinkedHashMap

7. 重写/重载

8. ==/equals

9. 抽象类 / 接口

10. sleep() / wait()

#### 2、常见异常

1. NullPointerException：空指针异常

   ```java
   public static void main(String[] args){
       int[] arr=null;
       System.out.println(arr[0]);//空指针异常
   }
   ```

2. ArrayIndexOutOfBoundsException：数组角标越界

   ```java
   public static void main(String[] args){
       int[] arr=new int[3];
       System.out.println(arr[3]);//数组角标越界
   }
   ```

3. ClassCastException类型转换异常

   ```java
   public static void main(String[] args){
       Object obj=new Date();
       String s=(String)obj;//类型转换异常
   }
   ```

4. NumberFormatException数值转换异常

   ```java
   public static void main(String[] args){
       String s="abc";
       int num=Intger.parseInt(s);//数值转换异常
   }
   ```

5. InputMismatchException输入类型异常

   ```java
   public static void main(String[] args){
       Scanner scanner=new Scanner(System.in);
       int score=scanner.nextInt();
       System.out.println(score);//输入“abc”，输入类型错误
   }
   ```

6. ArithmeticException算数异常

   ```java
   public static void main(String[] args){
       int a=10;
       int b=0;
       System.out.println(a/b);//算数异常
   }
   ```

#### 3、try-catch-finally

##### 异常的处理：抓抛模型

1. “抛”：程序在正常执行的过程中，一旦出现异常，就会在异常代码出生成一个对应异常类的对象并将此对象抛出，其后的代码就不再执行。
2. “抓”：可以理解为异常处理的方式：①try-catch-finally ②throws

##### try-catch-finally

```java
try{
    //可能出现异常的代码
}catch(异常类型1 变量名1){
    //处理异常的方式1
}catch(异常类型2 变量名2){
    //处理异常的方式2
}
......
finally{
    //一定会执行的代码
}

public static void main(String[] args){
    String s="abc";
    try{
        int num=Intger.parseInt(s);
        System.out.println("-----1-----");
    }catch(NumberFormatException e){
        System.out.println("出现数值转换异常");//出现异常时采取的操作
    }
    System.out.println("-----2-----");
}
//1不会输出，2会输出，因为一旦出现异常下面的代码就不再执行
```

1. finally是可选的，可以不写。

2. 使用try将可能出现异常的代码包装起来，在执行过程中，一旦出现异常，就会生成一个对应异常类的对象，根据此对象的类型去catch中进行匹配，一旦try中的对象匹配到某一个catch的时候就会进入异常的处理，一旦处理完成，如果没有写finally，就跳出当前的try-catch结构，继续执行其后的代码。

3. 对异常的常用操作：①getMessage()返回String；②printStackTrace()

   ```java
   public static void main(String[] args){
       String s="abc";
       try{
           int num=Intger.parseInt(s);
       }catch(NumberFormatException e){
           System.out.println(e.getMessage());//输出For input string: "abc"
            e.printStackTrace();//非常具体的异常的位置和信息
       }
   }
   ```

4. finally的使用：即使catch中也出现了异常，try和catch里面还有return语句，finally都会执行，就是不管怎样都一定会执行

   ```java
   public static void main(String[] args){
       int a=10;
       int b=0;
       try{
           System.out.println(a/b);//算数异常
       }catch(ArithmeticException e){
           e.printStackTrace();
       }finally{
           System.out.println("发生异常了");
       }
   }
   //输出：
   java.lang.ArithmeticException: / by zero
   at ExceptionExer.ExceptionTest.main(ExceptionTest.java:8)	
   发生异常了
   ```

5. finally的使用场景：数据库连接、输入输出流、网络编程Socket等资源，JVM是不能自动回收的，我们需要自己手动的进行资源释放，此时的资源释放需要声明在finally中。

6. try-catch-finally结构可以嵌套

7. 使用try-catch-finally处理编译时已成，使得程序在编译时不再报错，但运行时仍可能保持，相当于把编译时可能出现的异常延迟到运行时出现。一般不针对运行时异常使用try-catch-finally，针对编译时异常需要做处理。

#### 4、throws

```java
public static void main(String[] args){
    try{//main方法对异常进行处理
        method();
    }catch(ArithmeticException e){
        //处理
    }
}
public static void method() throws ArithmeticException{//抛到main方法
    int a=10;
    int b=0;
    System.out.println(a/b);//算数异常
}
```

throws异常类型写在方法的声明处，指明此方法执行时，可能会抛出的异常类型，一旦方法体执行时出现异常仍然会异常代码处生成一个异常类的对象，此对象满足throws后异常类型时就会被抛出，异常代码后续的代码就**不再执行**（和try-catch-finally的不同点）。

##### 方法重写的规则

子类重写的方法抛出的异常类型不大于父类被重写的方法抛出的异常类型

##### 开发中异常处理的选择

1. 如果父类中被重写的方法没有throws方式处理异常，则子类重写的方法也不能用throws
2. 执行的方法A中先后调用了其他方法，方法和方法之间又有递进关系，这几个方法用throws，A中用try-catch-finally

#### 5、手动抛出异常：throw

异常的产生：①自动生成 ②手动抛出

#### 6、用户自定义异常类

1. 继承于现有的异常结构：RuntimeException、Exception
2. 提供全局常量：serialVersionUID，序列版本号 
3. 提供重载的构造器

```java
public class EcDef extends Exception{
    static final long serialVersionUID=-33875164229948L;
    public EcDef(){
    }
    public EcDef(String msg){
        super(msg);
    }
}
```



















## 第8章 多线程

### Day 15 （P406-P427）

正式的多线程从P415开始

#### 1、程序、进程、线程

**程序**：一段静态的代码，静态对象

**进程**：正在运行的一个程序，是一个动态的过程，有生命周期。进程作为资源分配的单位，系统在运行时会为每个进程分配内存区域。

**线程**：进程可以进一步细化为线程，同一个进程可以支持多个线程就叫多线程

​		   线程作为调度和执行的单位，每个线程拥有独立的运行栈和程序计数器

![image-20211126110036164](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211126110036164.png)

每个线程各自有一套虚拟机栈和程序计数器

每个进程各有一份方法区和堆

**单核CPU和多核CPU**：一个JAVA应用程序至少有三个线程，main主线程，gc()垃圾回收线程，异常处理线程

**并行和并发**：并行——多个CPU同时执行多个任务

​					   并发——一个CPU同时执行多个任务

**多线程程序的优点：**

1、提高程序的响应。对图形化界面更有意义，可增强用户体验

2、提高计算机系统CPU的利用率

3、改善程序结构，进程分为线程独立运行，有利于理解和修改

#### 2、线程的创建和使用

##### 方式一：继承于Thread类

1、创建Thread类的子类

2、重写Thread类的方法

3、创建Thread类的子类对象

4、通过此对象调用start()

```java
class MyThread extends Thread{
    @Override
    public void run(){
        for (int i = 0; i < 10; i++) {
            System.out.println(i);
        }
    }
}
public static void main(String[] args) {
    MyThread t=new MyThread();
    t.start();//①启动当前线程 ②调用当前线程的run()
    //匿名子类
    new Thread(){
        @Override
        public void run(){
        }
    }.start();
}
//执行的先后顺序并不会按照写的先后顺序，两个线程是并行的
```

tips:

1. 不能通过run()的方式执行线程，用run()只是普通的调用方法
2. 如果还要再启动一个线程，就再新造一个MyThread对象，再start()

Thread里的常用方法：

1. start()：①启动当前线程 ②调用当前线程的run()
2. run()：通常需要重写此方法
3. currentThread()：静态方法，返回执行当前代码的线程
4. getName()：获取当前线程的名字
5. setName()：设置当前线程的名字
6. yield()：释放当前CPU的执行权
7. join()：在线程A中调用B的该方法，线程A进入阻塞状态直到线程B执行完之后线程A才继续执行
8. sleep()：让当前线程强制阻塞

线程的优先级：

1. MAX——10，MIN——1，NORM——5（默认的优先级）
2. 涉及的方法：getPriority()——返回线程的优先值，setPriority()——改变线程的优先级
3. 高优先级的线程不一定就先执行，只是大概率先执行

##### 方式二：实现Runnable接口

1. 创建一个实现Runnable接口的类
2. 实现类实现Runnable中的抽象方法：run()方法
3. 创建实现类的对象
4. 将对象作为参数传递到Thread类的构造器中，创建Thread类的对象
5. 通过此对象调用start()方法

```java
class MyRun implements Runnable{//创建一个实现Runnable接口的类
    @Override
    public void run(){//实现类实现Runnable中的抽象方法：run()方法
        for (int i = 0; i < 10; i++) {
            System.out.println(i);
        }
    }
}
public static void main(String[] args) {
    MyRun r=new MyRun();//创建实现类的对象
    Thread t=new Thread(r);//将对象作为参数传递到Thread类的构造器中，创建Thread类的对象
    t.start();//通过此对象调用start()方法
    
    //再启动一个线程
     Thread t1=new Thread(r);
     t1.start();
}
```

##### 两种方式的对比

1. Runnable没有单继承性的局限性，更适合多个线程共享数据的情况
2. 相同点：都需要重写run并且将线程要执行的逻辑声明在run()中

### Day 16（P428-P447）

#### 3、线程的生命周期

![image-20211201152708151](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211201152708151.png)

#### 4、线程的同步

线程安全问题：

- 多个线程执行的不确定性引起执行结果的不稳定性
- 多个线程对数据的共享会造成操作的不完整性，会破坏数据

解决：当一个线程A在操作共享数据的时候其他线程不能参与，直到线程A操作完毕，也就是同步机制。

##### 方式一：同步代码块

```java
synchronized(同步监视器){
    //需要被同步的代码
}
```

1. 操作共享数据的代码即为需要被同步的代码
2. 共享数据：多个线程共同操作的变量
3. 同步监视器，俗称锁。任何类的对象都可以充当锁，多个线程必须共用同一把锁。
4. 在实现Runnable接口创建多线程的方式中，我们可以考虑使用this充当同步监视器；而在继承Thread类创建多线程的方式中，可以考虑使用当前类

```java
//同步代码块+实现Thread类
class MyThread extends Thread{
    private static int ticket=100;
//实现Runnable接口由于后面只创建一个对象，所以可以用Object并且不加static关键字，实现Thread类每个进程要创建一个对象，创建多个对象，所以不是同一个Object，加上static关键字才是共有的
    @Override
    public void run(){
        synchronized (MyThread.class){//类只会加载一次
        //synchronized (this){
        //实现Runnable接口由于后面只创建一个对象实现Runnable接口创建多线程的方式用this，代表唯一的对象，实现Thread类每个进程要创建一个对象，创建多个对象，所以不能用this
        //synchronized(obj){//造了三个对象，有三把锁，所以不能保证线程安全,
            for (tikect>0) {
                System.out.println(getName()+"买票，票号为："+ticket);
                ticket--;
        	}
        }
    }
}
public static void main(String[] args) {
    MyThread t1=new MyThread();
    MyThread t2=new MyThread();
    MyThread t3=new MyThread();
    t1.start();
    t2.start();
    t3.start();
}
```

##### 方式二：同步方法

如果操作共享数据的代码完整的声明在一个方法中，不妨将此方法声明为同步的

```java
//同步方法+实现Runnable
class MyRun implements Runnable{
    private static int ticket=100;
    @Override
    public void run(){
        show();
    }
    public synchronized void show(){//这里的同步监视器就是this
        for (tikect>0) {
            System.out.println(getName()+"买票，票号为："+ticket);
            ticket--;
        }
    }
}
public static void main(String[] args) {
    MyRun r=new MyRun();
    
    Thread t1=new Thread(r);
    Thread t2=new Thread(r);
    Thread t3=new Thread(r);
    t1.start();
    t2.start();
    t3.start();
}
//同步方法+实现Thread类
class MyThread extends Thread{
    private static int ticket=100;
    @Override
    public void run(){
        show();
    }
    //如果不加static，那同步监视器是当前对象，必须是静态的,这里的同步监视器是当前类
    public static synchronized void show(){
        for (tikect>0) {
            System.out.println(Thread.currentThread.getName()+"买票，票号为："+ticket);
            ticket--;
        }
    }
}
```

##### 同步方法总结

非静态的同步方法，同步监视器是this，静态的同步方法，同步监视器是当前类本身

- 同步代码块

  - 继承Thread类：用当前类当作同步监视器（MyThread.class）

  - 实现Runnable接口：用this当同步监视器

- 同步方法

  - 实现Runnable接口：直接用synchronized修饰方法，this当同步监视器

  - 继承Thread类：需要用synchronized static修饰方法，当前类当同步监视器

##### 线程安全的单例模式：懒汉式

```java
class MyThread extends Thread{
    @Override
    public void run(){
        Bank.getInstance();
    }
}
class Bank{
    private Bank(){

    }
    private static Bank instance=null;
    //方法1:同步方法
    public static synchronized Bank getInstance(){//加上synchronized
        if (instance==null)instance=new Bank();
        return instance;
    }
    //方法2:同步代码块（效率稍差）
    public static Bank getInstance(){
        synchronized(Bank.class){
            if (instance==null)instance=new Bank();
            return instance;
        }
    }
    //效率更高
    public static Bank getInstance(){
        if (instance==null){
            synchronized(Bank.class){
                if (instance==null)instance=new Bank();
                return instance;
            }
        }
    }
}
```

##### 死锁

不同的线程分别占用对方需要的同步资源不放弃，都在等待对方放弃，造成了线程的死锁，没有异常没有提示，但所有线程都在阻塞状态。

解决：①专门的算法、原则；②尽量减少同步资源的定义；③尽量避免嵌套同步

##### Lock（锁）

从JDK5.0开始，JAVA提供了更强大的线程同步机制——通过显式定义同步锁来实现同步，同步锁使用Lock对象充当。java.util.concurrent.locks.Lock接口是控制多个线程对共享资源进行访问的工具。

```java
class MyRun implements Runnable{
    private static int ticket=100;
    //1.实例化ReentrantLock
    private ReentrantLock lock=new ReentrantLock(true);
    @Override
    public void run(){
        try {
            //2.调用lock()方法
            lock.lock();
            while (ticket>0){
                try {
                    Thread.sleep(100);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println(Thread.currentThread().getName()+"票号为："+ticket);
                ticket--;
            }
        }finally {
            //3.调用解锁的方法
            lock.unlock();
        }
    }
}
//如果是继承Thread方式，private static ReentrantLock lock=new ReentrantLock(true)要加static
```

面试题：

1、synchronized和lock的不同：

1. Lock是显式锁(手动开启和关闭锁，别忘记关闭锁)，synchronized是隐式锁，出了作用域自动释放

2. Lock只有代码块锁，synchronized有代码块锁和方法锁
3. 使用Lock锁，JVM将花费较少的时间来调度线程，性能更好，并且具有更好的扩展性(提供更多的子类)

2、优先使用顺序:

Lock >同步代码块(已经进入了方法体，分配了相应资源) >同步方法(在方法体之外）

3、解决线程安全问题

synchronized（分为同步代码块和同步方法）和锁

#### 5、线程的通信

```java
class MyRun implements Runnable{
    private static int num=1;
    @Override
    public void run(){
        while (true){
            synchronized (this){
                notify();//*********
                if (num<=100){
                    try {
                        Thread.sleep(100);
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                    System.out.println(Thread.currentThread().getName()+"当前数字："+num);
                    num++;
                    try {
                        wait();//*********
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
            }
        }
    }
}
```

- 涉及的三个方法：

  1. wait()：强制当前线程等待，直到某个其他线程在同一个对象上调用notify()或notifyAll()

  1. notify()：唤醒wait中的一个线程，如果有多个线程被阻塞，则唤醒优先级高的那个

  1. notifuAll()：唤醒所有wait中的线程

- 说明：

  1. 三个方法必须使用在同步代码块或者同步方法中
  2. 三个方法的调用者必须是同步监视器，否则会出现IllegalMonitorStateException异常
  3. 三个方法声明在Object类中

- 面试题：sleep()和wait()的异同

  相同点：一旦执行方法，都可以使当前线程进入阻塞状态

  不同点：

  1. 声明位置不同，sleep()声明在Thread类中，wait()声明在Object类中
  2. 调用的要求不同，sleep()可以在任何需要的场景下调用，wait()必须在同步代码块或者同步方法中
  3. 关于**是否释放同步监视器**，如果两个方法都使用在同步代码块或者同步方法中，wait()会释放同步监视器

##### 经典例题:生产者/消费者问题

ps:建议多看这个视频加深理解P443

●生产者(Productor)将产品交给店员(Clerk),而消费者(Customer)从店员处取走产品，店员一次只能持有固定数量的产品(比如:20)，如果生产者试图生产更多的产品，店员会叫生产者停一下，如果店中有空位放产品了再通知生产者继续生产:如果店中没有产品了，店员会告诉消费者等一下，如果店中有产品了再通知消费者来取走产品。

●这里可能出现两个问题:

➢生产者比消费者快时，消费者会漏掉一些数据没有取到。

➢消费者比生产者快时，消费者会取相同的数据。

我理解的线程安全问题：两个线程分别生产和消费，但是操作了共同数据那就是产品，所以会出现线程安全问题，就是必须规定一段时间内只能生产或者只能消费

#### 6、JDK5.0新增线程创建方式

##### 实现Callable接口

1、与使用Runnable相比， Callable功能更强大些 

- 相比run方法， 可以有返回值
- 方法可以抛出异常
- 支持泛型的返回值 
- 需要借助FutureTask类， 比如获取返回结果

2、Future接口

- 可以对具体Runnable、Callable任务的执行结果进行取消、查询是否完成、获取结果等。
- FutrueTask是Futrue接口的唯一的实现类
- FutureTask 同时实现了Runnable, Future接口。它既可以作为Runnable被线程执行，又可以作为Future得到Callable的返回值

```java
//1.创建一个实现Callable类的实现类
class MyCall implements Callable{
    //2.实现call方法，将此线程需要执行的操作声明在call方法中
    @Override
    public Object call() throws Exception {
        return 1;
    }
}
public static void main(String[] args) {
    //3.创建Callable实现类的对象
    MyCall myCall=new MyCall();
    //4.将Callable实现类的对象传递到FutureTask构造器中，创建FutureTask的对象
    FutureTask<Integer> myTask=new FutureTask<Integer>(myCall);//可以使用泛型
    //5.将FutureTask的对象传递到Thread构造器中并调用start方法
    new Thread(myTask).start();//启动线程还是要用start()方法
    //6.get()返回值即为FutureTask构造器参数Callable实现类重写的call()的返回值
    try {
        myTask.get();//可以得到返回值1
    } catch (InterruptedException e) {
        e.printStackTrace();
    } catch (ExecutionException e) {
        e.printStackTrace();
    }
}
```

##### 使用线程池

开发中都是用线程池，好处：

- 减少创建新线程的时间，提高响应速度
- 重复利用线程池中的线程降低资源消耗
- 便于线程管理

1、JDK 5.0起提供了线程池相关API: ExecutorService 和Executors

2、ExecutorService:真正的线程池接口。常见子类ThreadPoolExecutor

- void execute(Runnable command):执行任务/命令，没有返回值，一般用来执行Runnable
- <T> Future<T> submit(Callable<T> task); 执行任务，有返回值，一般又来执行Callable
- void shutdown():关闭连接池

3、Executors: 工具类、线程池的工厂类，用于创建并返回不同类型的线程池 ➢Exefutors newCachedThreadPool():创建一个可根据需要创建新线程的线程池 ➢Executors .newFixedThreadPool(n);创建一个可重用固定线程数的线程池

- Executors. newSingleThreadExecutor): 创建一个只有一个线程的线程池
- Executors newScheduledThreadPool(n): 创建一个线程池，它可安排在给定延迟后运行命令或者定期地执行

```java
public static void main(String[] args) {
    //1.提供指定数量的线程池
    ExecutorService service= Executors.newFixedThreadPool(10);
    //2.执行指定的线程的操作，需要提供实现Runnable接口或者Callable接口实现类的对象
    service.execute(new NumberThread());//适用于Runnable
    service.submit(new MyCall());//适用于Callable
    service.shutdown();//3.关闭连接池
}
class NumberThread implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i < 100; i++) {
            if (i%2==0)System.out.println(i);
        }
    }
}
class MyCall implements Callable{
    @Override
    public Object call() throws Exception {
        return 1;
    }
}
```

#### 7、总结

1、创建多线程有四种方式：

- 继承Thread类
- 实现Runnable接口
- 实现Callable接口
- 使用线程池

2、同步的方式：

- 同步代码块

  - 继承Thread类：用当前类当作同步监视器（MyThread.class）

  - 实现Runnable接口：用this当同步监视器
- 同步方法

  - 继承Thread类：直接用synchronized修饰方法，this当同步监视器
  - 实现Runnable接口：需要用synchronized static修饰方法，当前类当同步监视器
- 定义同步锁

3、释放锁的操作

- 当前线程的同步方法、同步代码块执行结束。
- 当前线程在同步代码块、同步方法中遇到break、returm终止了该代码块、该方法的继续执行。
- 当前线程在同步代码块、同步方法中出现了未处理的Error或Exception,导致异常结束。
- 当前线程在同步代码块、同步方法中执行了线程对象的wait()方法，当前线程暂停，并释放锁。

4、不会释放锁的操作

- 线程执行同步代码块或同步方法时，程序调用Thread sleep()、 Thread. yield()方法暂停当前线程的执行
- 线程执行同步代码块时，其他线程调用了该线程的suspend()方法（挂起）将该线程挂起，该线程不会释放锁(同步监视器)

ps:应尽量避免使用suspend()和resume()来控制线程

## 第9章 JAVA常用类

### 1、字符串相关的类

#### String类及常用方法

1. String定义了final char[] value用于存储字符串数据，代表不可变的字符序列。

   - 对字符串重新赋值时，需要重写指定内存区赋值，不能使用原有的value进行赋值
   - 当对现有的字符串进行连接操作时，也需要重新指定内存区域赋值，不能使用原有的value进行赋值

2. String实现了Serializable接口：表示字符串是支持序列化的。实现了Comparable接口，表示String可以比较大小

3. 通过字面量的方式给一个字符串赋值，此时字符串值声明在字符串常量池中，字符串常量池中是不会存储相同内容的字符串的

   ```java
   String st1="abc";//字面量，存储在字符串常量池中，目的是共享
   String st2=new String("abc");//字符串非常量对象存储在堆中
   ```

4. 面试题：`String s=new String("abc")`方式创建对象，在内存中创建了几个对象？

   两个，一个是堆空间中new的结构，另一个是`char[]`对应常量池中的数据“abc”

5. 不同拼接操作的对比

   ```java
   String s1="leet";
   String s2="Code";
   
   String s3="leetCode";
   String s4="leet"+"Code";
   String s5=s1+"Code";
   String s6="leet"+s2;
   String s7=s1+s2;
   
   String s8=s5.intern();//返回值得到的s8使用的是常量池中的字符串
   
   s3==s4;//true，都是在常量池中
   s3==s5;//false，只要有变量参与，都在堆中
   s3==s6;//false
   s3==s7;//false
   ```

   结论：

   1. 常量与常量的拼接结果在常量池，且常量池中不会存在相同容量的常量
   2. 只要其中有一个是变量，结果就在堆中

6. JVM中涉及字符串的内存结构

   ![image-20211204204821092](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211204204821092.png)

7. String中的方法

   ```java
   int length();
   char charAt(int index);
   boolean isEmpty();
   String toLowerCase();//转小写
   String toUpperCase();//转大写，字符串本身不变，需要新建字符串接收
   String trim();//去除收尾空格
   boolean equals();
   boolean equalsIgnoreCase();//和equals类似，忽略大小写
   int CompareTo();//比较两个字符串的大小，负数则当前字符串小
   String subString();
   boolean endsWith();//是否以指定的字符串结束
   boolean startsWith(String prefix,int toffset);//指定索引位置开始的子字符串是否以指定前缀开始
   ```

8. String和其他基本数据类型和包装类的转换

   String--->基本数据类型、包装类：调用包装类的静态方法parseXxx(str)

   基本数据类型、包装类--->String：调用String重载的valueOf(xxx)

9. String和char[]的转换

   String--->char[]：str.toCharArray

   char[]--->String：调用String的构造器

10. String和byte[]的转换

    String--->byte[]：调用String的getBytes()方法

    byte[]--->String：调用String的构造器

11. ```java
    final String s1="leet";
    String s2="Code";
    String s3="leetCode";
    String s4=s1+"Code";
    s3==s4;//true,因为s1是常量，操作在常量池中
    ```

#### StringBuffer/StringBuilder

1. String、StringBuffer和StringBuilder的区别？

   String：不可变的序列，底层使用char[]存储

   StringBuffer：可变的序列，线程安全，效率稍低，底层使用char[]存储

   StringBuilder：可变的序列，线程不安全，效率稍高，底层使用char[]存储

   效率：StringBuilder > StringBuffer > String

   String----->StringBuffer和StringBuilder:调用StringBuffer和StringBuilder的构造器

   StringBuffer和StringBuilder----->String:调用String的构造器

2. 源码分析

   ```java
   String str=new String();//new char[0]
   String str=new String("abc");//new char['a','b','c']
   StringBuffer sb=new StringBuffer();//char[] value=new char[16],底层造了一个长度为16的数组
   StringBuffer sb1=new StringBuffer("abc");//char[] value=new char["abc".length()+16];
   问题1：System.out.println(sb1.length());//输出3而不是19
   问题2：如果要添加的数据底层数组撑不下了，默认情况下会扩容为原来容量的2倍+2，同时将原来数组的元素赋值到新的数组中
   ```

### 2、JDK8之前的日期时间API

#### System静态方法

```java
System.currentTimeMillis();//返回当前时间与1970年1月1日0时0分0秒之间以毫秒为单位的时间差，时间戳
```

#### Date类

 1、java.util.Date类

表示特定的瞬间，精确到毫秒

- 构造器

Date():使用无参构造器创建的对象可以获取本地当前时间。

Date(long date)：创建指定毫秒数的对象

- 常用方法

getTime():返回自1970 年1月 1 日 00:00:00 GMT 以来此Date对象表示的毫秒数。

toString()：把Date 对象转换为以下形式的String: dow mon dd hh:mm:ss zzz yyy其中: dow 是一周中的某一天(Sun, Mon, Tue, Wed, Thu, Fri, Sat), zzz是时间标准 

其它很多方法都过时了

2、 java.sql.Date类对应数据库中的日期类型的变量

-  实例化：java.sql.Date date=new  java.sql.Date();

-  将util.Date类转化为sql.Date类，sql.Date类是util.Date类的子类

```java
Date date=new java.sql.Date(3253834753L);//多态
java.sql.Date date1= (java.sql.Date) date;//强转

Date date=new Date();
java.sql.Date date1= (java.sql.Date) date;//父类对象强转运行会报错
java.sql.Date date1= new java.sql.Date(date.getTime());
```

#### Calendar类

java.util.Calendar(日历)类

Calendar是一个抽象基类，主用用于完成日期字段之间相互操作的功能。

- 获取Calendar实例的方法

使用Calendar.getInstance()方法

调用它的子类GregorianCalenda的构造器

●一个Calendar的实例是系统时间的抽象表示，通过get(int field)方法来取得想要的时间信息。比如YEAR、MONTH、DAY _OF WEEK、HOUR OF DAY、。MINUTE、SECOND

➢public void set(int field,int value)

➢public void add(int field,int amount)

➢public final Date getTime()

➢public final void setTime(Date date)

➢获取月份时：一月是0，二月是1，以此类推，12月是11

➢获取星期时：周日是1,周二是2，。。。。周六是7

#### SimpleDateFormat类

SimpleDateFormat的使用：排队日期Date类的格式化和解析，格式化：日期--->字符串，解析：字符串--->日期

```java
public static void main(String[] args) {
    SimpleDateFormat simpleDateFormat = new SimpleDateFormat();
    Date date = new Date();
    System.out.println(date);//输出Sun Dec 05 14:28:58 CST 2021
    //格式化
    String format = simpleDateFormat.format(date);
    System.out.println(format);//输出21-12-5 下午2:28
    //解析
    String s="21-12-5 下午2:31";
    Date parse = simpleDateFormat.parse(s);
    System.out.println(parse);
}
```

练习题1：将字符串"2020-09-08"转换为java.sql.Date

```java
String s="2020-09-08";
SimpleDateFormat s1 = new SimpleDateFormat("yyyy-MM-dd");
Date date1=s1.parse(s);
java.sql.Date date2=new java.sql.Date(date1.getTime());
```

练习题2：三天打鱼两天晒网，1990-01-01，2020-09-08打鱼还是晒网，其实就是求总天数

```java
public static void main(String[] args) throws ParseException {
    SimpleDateFormat s1=new SimpleDateFormat("yyyy-MM-dd");
    Date date1=s1.parse("1999-01-01");
    Date date2=s1.parse("2020-09-08");
    Long day=(date2.getTime()-date1.getTime())/(1000*60*60*24);
    Long res=day%5;
    System.out.println(res);
}
```

### 3、JDK8中新日期时间API

#### LocalDate/LocalTime/LocalDateTime

LocalDateTime最常用

#### Instant

时间线上的一个瞬时点

#### DateTimeFormatter

```java
DateTimeFormatter.ofPattern("yyyy-MM-dd hh:mm:ss")
```

#### 其他类

### 4、JAVA比较器

#### Comparable接口

自然排序

#### Comparator接口

定制排序：重写compare(Object o1,Object o2)方法比较大小v  

### 5、System类 

### 6、Math类

### 7、BigInteger与BigDecimal

BigInteger可以表示不可变的任意精度的整数

要求数字精度比较高，会用到BigDecimal

## 第10章 枚举类&注解

### 枚举类

### 1、如何自定义枚举类

当一个类的对象只有有限确定个数时我们称此类为枚举类，当需要定义一组常量时强烈建议用枚举类

JDK5.0之前，自定义枚举类

```java
class Season{
    //1.声明Season对象的属性：private final修饰
    private final String seasonName;
    private final String seasonDesc;
	//2.私有化类的构造器，并给对象属性赋值
    private Season(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }
	//3.提供当前枚举类的多个对象：public static final
    public static final Season SPRING=new Season("春天","春暖花开");
    public static final Season SUMMER=new Season("夏天","夏日炎炎");
    public static final Season AUTUMN=new Season("秋天","秋高气爽");
    public static final Season WINTER=new Season("冬天","冰天雪地");
}
```

### 2、如何使用关键字enum定义枚举类

JDK5.0之后，可以使用enum关键字定义枚举类

默认继承于class java.lang.Enum

```java
enum Season1{
    SPRING("春天","春暖花开"),
    SUMMER("夏天","夏日炎炎"),
    AUTUMN("秋天","秋高气爽"),
    WINTER("冬天","冰天雪地");
    private final String seasonName;
    private final String seasonDesc;

    private Season1(String seasonName, String seasonDesc) {
        this.seasonName = seasonName;
        this.seasonDesc = seasonDesc;
    }
}
```

### 3、Enum类的主要方法

values()方法: 返回枚举类型的对象数组，该方法可以很方便地遍历所有的枚举值

valueOf(String str):可以把一个字符串转为对应的枚举类对象。 要求字符面串必须是枚举类对象的“名字”。如不是，会有运行时异常:llegalArgumentException.

toString(): 返回当前枚举类对象常量的名称

### 4、实现接口的枚举类

1. 在enum类中实现抽象方法，和一般类相同

2. 每一个对象可以重写方法

   ```java
   interface Info{
       void show();
   }
   enum Season1 implements Info{
       SPRING("春天","春暖花开"){
           @Override
           public void show() {
               
           }
       },
       SUMMER("夏天","夏日炎炎") {
           @Override
           public void show() {
               
           }
       },
       AUTUMN("秋天","秋高气爽") {
           @Override
           public void show() {
               
           }
       },
       WINTER("冬天","冰天雪地") {
           @Override
           public void show() {
               
           }
       };
       private final String seasonName;
       private final String seasonDesc;
   
       private Season1(String seasonName, String seasonDesc) {
           this.seasonName = seasonName;
           this.seasonDesc = seasonDesc;
       }
   }
   ```

### 注解

1、注解概述:P505

2、常见的Annotation示例

@Overide @Deprecated @SuppressWarnings

3、自定义Annotation

参照SuppressWarnings定义

①注解声明为: @interface

②内部定义成员，通常使用value表示

③可以指定成员的默认值， 使用default定义

④如果自定义注解没有成员，表明是一个标识作用。

自定义注解必须使用反射才有意义

4、JDK中的四种元注解

用于修饰其他注解

**Retention**：指定所修饰的Annotation的生命周期：SOURCE/CLASS(默认行为)/RUNTIME

只有声明为RUNTIME生命周期的注解才能通过反射获取

**Target**：用于指定被修饰的Annotation能用于修饰哪些程序元素

------------以下出现频率较低

**Documented**：表示所修饰的注解在被javadoc解析时保留下来

**Inherited**：所修饰的注解具有继承性

5、利用反射获取注解信息

6、JDK8中注解的新特性：可重复注解、类型注解

**可重复注解**：

① 在MyAnnotation上声明@Repeatable，成员值为MyAnnotation.class

② MyAnnotation的Target和Retention等元注解必须和Annotations相同

**类型注解**：

➢ElementType.TYPE_PARAMETER表示该注解能写在类型变量的声明语句中(如:泛型声明)

➢ElementType.TYPE_USE表示该注解能写在使用类型的任何语句中。

## 第11章 JAVA集合

### 1、JAVA集合框架概述

Java集合可以分为两种体系：

- **Collection接口**：单列数组

List：元素有序、可重复的集合——ArrayList\LinkedList\Vector

Set：元素无序、不可重复的集合——HashSet\LinkedHashSet\TreeSet

- **Map接口**：具有映射关系的“key-value”集合——**HashMap**\LinkedHashMap\TreeMap\Hashtable\Properties

![image-20211208142527668](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211208142527668.png)

### 2、Collection接口方法

1. contains()用的是equals方法，如果是String对象，重写过那就是比较内容，不然就是比较地址

2. retainAll相当于是求交集

3. hashCode()：求哈希值

4. toArray()：集合---->数组

5. Arrays.asList()：数组----->集合

   ```java
   List<int[]> list1 = Arrays.asList(new int[]{123, 456});
   List<Integer> list = Arrays.asList(new Integer[]{123, 456});//要用包装类
   ```

6. iterator()：返回iterator接口的实例，用于遍历集合元素

### 3、Iterator迭代器接口

```java
Collection coll=new ArrayList();
coll.add(123);
coll.add(456);
Iterator iterator = coll.iterator();
while(iterator.hasNext()){
    System.out.println(iterator.next());//输出1
}
iterator.remove();//迭代器也有remove方法
```

jdk 5.0新增了foreach循环，用于遍历集合和数组

### 4、Collection子接口一：List

面试题：ArrayList\LinkedList\Vector三者异同？

相同：都实现了List接口，存储数据的特点相同

不同：ArrayList——List接口的主要实现类，执行效率高，线程不安全，底层使用Object[]存储

LinkedList——使用双向链表存储，对于频繁的插入删除操作效率比ArrayList高

Vector——执行效率低，线程安全，底层使用Object[]

#### ArrayList源码分析

1. jdk 7情况下：

   ArrayList list = new ArrayList();//底层创建了长度是1的Object[]数组eLementData

   list. add(123);//eLementData[e] = new Integer(123);

   list. add(11);//如果此次的添加导致底层eLementData数组容量不够，则扩容。

   默认情况下，扩容为原来的容量的1.5倍，同时需要将原有数组中的数据复制到新的数组中。

   结论:建议开发中使用带参的构造器: ArrayList list = new Arraylist(int capacity)

2. jdk 8中ArrayList的变化:

   Arraylist list = new ArrayList();//底层Object[] elementData 初始化为{}.并没有创建长度

   list. add(123);//第一次调用add()时，底层才创建了长度10的数组

   后续的添加和扩容与jdk7无异

#### LinkedList源码分析

是双向链表

### 5、Collection子接口二：Set

- HashSet：线程不安全，可以存储null值，底层是HashMap

- LinkedHashSet：遍历数据是可以按照添加的顺序顺序遍历

- TreeSet：可以按照添加对象的指定属性进行排序，底层是用红黑树储存的

1. 无序性：不等于随机性，是存储的数据在底层数组中并非按照索引添加，而是按照哈希值添加
2. 不可重复性：本质上使用equals做的比较

#### HashSet

我们向HashSet中添加元素,首先调用元素a所在类的hashCode()方法，计算元素a的哈希值，此哈希值接者通过某种算法计算出在HashSet底层数组中的存放位置(即为:索引位置)，判断数组此位置上是否已经有元素。

- 如果此位置上没有其他元素，则元素a添加成功。


- 如果此位置上有其他元素b(或以链表形式存在的多个元素)，则比较元素a与元素的hash值:

  - 如果hash值不相同，则元素a添加成功。


  - 如果hash值相同，进而需要调用元素a所在类的equlas()方法:


equals()返回true,元素a添加失败

equals()返回false,则元素七上八下，JDK7之前是在当前元素之前，JDK8之后是在当前元素之后

像set中添加的数据其所在的类一定要重写hashCode()和equals()并保持一致性，直接用系统生成的

#### LinkedHashSet

是HashSet的子类因为是有序的，所以频繁遍历的效率高于HashSet

#### TreeSet

添加的数据必须是相同类型的对象

排序可以自然排序（实现compareble接口）和定制排序，自然排序中比较对象是否相同的标准为compareTo()返回0而不是equals()

### set习题

```java
public static void main(String[] args) throws ParseException {
    HashSet set=new HashSet();
    Person p1=new Person("AA",1001);
    Person p2=new Person("BB",1002);
    set.add(p1);
    set.add(p2);
    p1.name="CC";//将AA 1001对应哈希值的位置改了属性
    set.remove(p1);//找CC 1001对应的哈希值删除，结果没找到
    System.out.println(set);//还是输出两个元素
    set.add(new Person("CC",1001));//放入CC 1001对应哈希值的位置
    System.out.println(set);
    set.add(new Person("AA",1001));//找到AA 1001对应哈希值的位置，但该位置放的是CC，所以成功添加
    System.out.println(set);
}
static class Person{
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public Person() {
    }

    @Override
    public String toString() {
        return "Person{" +
            "name='" + name + '\'' +
            ", age=" + age +
            '}';
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Person person = (Person) o;
        return age == person.age && Objects.equals(name, person.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }
}
```

### 6、Map接口

#### Map实现类结构

<img src="C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211208142444965.png" alt="image-20211208142444965" style="zoom: 67%;" />



- HashMap：Map的主要实现类，线程不安全，效率高，可以存储null的key和value
  - LinkedHashMap：在原有的HashMap底层结构上添加了一堆指针指向前一个和后一个元素，保证在遍历元素时按照添加的顺序实现遍历，对于频繁的遍历操作，此类执行效率高于HashMap

- TreeMap：保证按照添加的key-value对进行排序，实现排序遍历，使用key的自然或者定制排序

- Hashtable：作为古老的实现类，线程安全效率低，不能存储null的key和value
  - Properties：Properties 类是 Hashtable 的子类，该对象用于处理属性文件，由于属性文件里的 key、value 都是字符串类型，所以 Properties 里的 key  和 value 都是字符串类型

HashMap底层：数组+链表（JDK7之前

​							数组+链表+红黑树（JDK8

面试题：

1. HashMap底层实现原理？
2. HashMap和Hashtable的异同？
3. CurrentHashMap与Hashtable的异同？

#### Map结构

Map中的key:无序的、不可重复的，使用Set 存储所有的key，key所在类要重写equals和hashCode方法

Map中的value:无序的、可重复的，使用Collection 存储所有的vaLue

一个键值对: key-value 构成了一个Entry对象。

Map中的entry:无序的、不可重复的，使用set存储所有entry

#### HashMap JDK7

##### 底层实现

```java
HashMap map=new HashMap();
//在实例化以后，底层创建了长度是16的一维数组Entry[] table
map.put(key1,value1);
```

首先调用Key1所在类的hashCode方法计算key1哈希值，哈希值经过计算之后得到Entry数组中的存放位置

1. 如果数据为空，添加成功
2. 如果此位置上的数据不为空，(意味着此位置上存在一个或多个数据(以链表形式存在，JDK放在上面，就是当前添加的数据的next是原来的数据))，比较key1和已经存在的一个或多个数据的哈希值:
   1. 如果key1的哈希值与己经存在的数据的哈希值都不相同，此时key1-value1添加成功。
   2. 如果key1的哈希值和已经存在的某一个数据的哈希值相同， 继续比较:调用key1所在类的equals()方法，比较: 
      1. 如果equals()返回false:此时key1-value1添加成功
      2. 如果equals()返@true:使用新value替换旧value

在添加过程中会涉及到扩容问题，默认扩容为原来的2倍，之前的数据需要重新计算存放位置

##### 源码分析

P552

#### HashMap JDK8

##### 底层实现

相较于JDK7 底层实现的不同：

1. new HashMap():底层没有创建-一个长度为16的数组

2. jdk 8底层的数组是: Node[], 而非Entry[]

3. 首次调用put()方法时，底层创建长度为16的数组

4. JDK7：数组+链表，JDK8：数组+链表+红黑树

   当数组的某一个索引位置上的元素以链表形式存在的数据个数>8且当前数组的长度>64，此时所以位置上的所有数据改为红黑树存储（查找效率高很多

##### 源码分析

DEFAULT_ INITIAL_ CAPACITY : HashMap的默认容量，16

DEFAULT_ LOAD FACTOR: HashMap的默认加载因子: 0.75

threshold:扩容的临界值，=容量*填充因子: 16 * 0.75 => 12

TREEIFY THRESHOLD: Bucket 中链表长度大于该默认值，转化为红黑树:8 

MIN TREEIFY CAPACITY:桶中的Node被树化时最小的hash表容量:64

#### LinkedHashMap

PS:了解就可以了

HashMap中的内部类：Node

```java
static class Node<K,V> implements Map.Entry<K,V> {
    final int hash;
    final K key;
    V value;
    Node<K,V> next;
}
```

LinkedHashMap中的内部类：Entry

```java
static class Entry<K,V> extends HashMap.Node<K,V> {
    Entry<K,V> before, after;
    Entry(int hash, K key, V value, Node<K,V> next) {
    	super(hash, key, value, next);
	}
}
```

#### Map中定义的方法

元视图操作的方法： 

Set keySet()：返回所有key构成的Set集合 

```java
Set set=map.keySet();
```

Collection values()：返回所有value构成的Collection集合 

Set entrySet()：返回所有key-value对构成的Set集合

#### TreeMap

TreeMap存储 Key-Value 对时，需要根据 key-value 对进行排序。

 TreeMap 可以保证所有的 Key-Value 对处于有序状态。

TreeSet底层使用红黑树结构存储数据 

TreeMap 的 Key 的排序：

- 自然排序：TreeMap 的所有的 Key 必须实现 Comparable 接口，而且所有 的 Key 应该是同一个类的对象，否则将会抛出 ClasssCastException 

- 定制排序：创建 TreeMap 时，传入一个 Comparator 对象，该对象负责对 TreeMap 中的所有 key 进行排序。此时不需要 Map 的 Key 实现 Comparable 接口

TreeMap判断两个key相等的标准：两个key通过compareTo()方法或 者compare()方法返回0。

#### Properties 

Properties 类是 Hashtable 的子类，该对象用于处理属性文件，由于属性文件里的 key、value 都是字符串类型，所以 Properties 里的 key  和 value 都是字符串类型

### 7、Collections工具类

Collections 是一个操作 Set、List 和 Map 等集合的工具类

Collection和Collections的区别?Collection是接口，Collections是工具类

- void copy(List dest,List src)：将src中的内容复制到dest中

```java
List list=new ArrayList();
list.add(123);
list.add(345);
List list1=new ArrayList();
Collections.copy(list1,list);//IndexOutOfBoundsException: Source does not fit in dest
//lsit1容量比list小
List list1=Arrays.asList(new Object[list.size()]);//这样就容量一样了
```

- Collections 类中提供了多个 synchronizedXxx() 方法，该方法可使将指定集 合包装成线程同步的集合，从而可以解决多线程并发访问集合时的线程安全 问题

## 第12章 泛型

### 1、为什么要有泛型

任何类型都可以添加到集合中：类型不安全

读取出来的对象需要强转：繁琐，可能有ClassCastException

### 2、在集合中使用泛型

集合类或者集合接口都在JDK5.0的时候修改为带泛型的结构

泛型的类型必须是类，如果是基本数据类型则用包装类

### 3、自定义泛型结构

泛型类/泛型接口

```java
//泛型类，如果定义了泛型类，实例化时没有指明类型，则认为此时泛型类型为Object类型
public class Order<T>{
    String name;
    int age;
    T orderT;

	public Order(String name, int age, T orderT) {
    this.name = name;
    this.age = age;
    this.orderT = orderT;
	}	
}
```

由于子类在继承带泛型的父类时同样继承了泛型，新建对象时不需要指明泛型，此时子类不是泛型类

泛型方法

在方法中出现了泛型的结构，泛型参数与类的泛型参数没有任何关系，泛型方法所属的类是不是泛型类都没有关系

```java
public <E> List<E> pro(E[] arr){}
```

### 4、泛型在继承上的体现

如果B是A的一个子类型（子类或者子接口），而G是具有泛型声明的类或接口，`G<B>`**并不是**`G<A>`的子类型

### 5、通配符的使用

List<?>是List<Integer>、List<Long>等各种泛型List的父类

list<?>不能向其内部添加数据。因为我们不知道c的元素类型，我们不能向其中添加对象，**null除外**

有限制条件的通配符的使用：

？extends Person：<=

?  super Person：>=

## **第13章IO流**

### 1、File类的使用

```java
public static void main(String[] args){
    File file=new File("hello.txt");
    System.out.println(file);//hello.txt
    File file1 = new File("\"C:\\Users\\86187\\Desktop\\hotel.txt\"");
    System.out.println(file1);//"C:\Users\86187\Desktop\hotel.txt"
    File file2 = new File("\"C:\\Users\\86187\\Desktop\"","JavaSenior");
    System.out.println(file2);//"C:\Users\86187\Desktop"\JavaSenior
    File file3 = new File(file2,"hi.txt");
    System.out.println(file3);//"C:\Users\86187\Desktop"\JavaSenior\hi.txt
}
```

1. File类的一个对象，代表一个文件或者一个文件目录

   ```java
   File(String filePath)
   File(String parentPath,String childPath)
   File(File parentFile,String childPath)
   ```

2. File类声明在java.io包下，路径可以分为相对路径和绝对路径

   相对：相较于某个路径下指明的路径

   绝对：包含盘符在内的文件或者文件目录的路径

3. 常用方法

   涉及到关于文件或文件目录的创建、删除、重命名、修改时间、文件大小等方法，并未涉及到写入或读入文件内容的操作，如果需要读取或写入文件内容，必须使用IO流来完成

4. 后续File类的对象通常会作为参数传递到流的构造器中，指明读取或者写入的终点

### 2、IO流原理及流的分类

- 按操作数据单位不同分为：字节流(8 bit)，字符流(16 bit) 

- 按数据流的流向不同分为：输入流，输出流 

- 按流的角色的不同分为：节点流，处理流

<img src="C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211210142652719.png" alt="image-20211210142652719" style="zoom:50%;" />

重点：缓冲流、转换流、对象流

了解：标准打印输入、输出流、打印流、数据流、随机存取文件流，NIO.2

<img src="C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211211125620004.png" alt="image-20211211125620004" style="zoom:67%;" />

### 3、节点流（或文件流）

#### 读入

1. read()的理解: 返回读入的一个字符。如果达到文件末尾，返回-1
2. 异常的处理:为了保证流资源定可以执行关闭操作。需要使用try-catch-finally处理
3. 读入的文件定要存在， 否则就会报FileNotFoundException

```java
public static void main(String[] args){
    FileReader fR=null;
    try {
        //1、实例化File类的对象，指明要操作的文件
        File file = new File("hello.txt");
        System.out.println(file.getAbsolutePath());
        //2、提供具体的流
        fR = new FileReader(file);
        //3、数据的读入
        //read()返回读入的一个字符，如果达到文件末尾返回-1
        int data;
        while ((data=fR.read())!=-1){
            System.out.println(data);
        }
    }catch (IOException e){
        e.printStackTrace();
    }finally {
        //4、流的关闭
        try {
            if (fR!=null)fR.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 写出

1.创建流对象，建立数据存放文件，文件可以不存在，不会报异常，会自动创建此文件

- FileWriter(file,false)/ FileWriter(file)会对原有文件进行覆盖

- FileWriter(file,true)会在原文件基础上追加

2.调用流对象的写入方法，将数据写入流 

3.关闭流资源，并将流中的数据清空到文件中

```java
public void testFileWriter() throws IOException {
    File file= new File("hello1.txt");
    FileWriter fw=new FileWriter(file);
    fw.write("I have a dream");
    fw.close();
}
```

- 字节流操作字节，比如：.mp3，.avi，.rmvb，mp4，.jpg，.doc，.ppt 

- 字符流操作字符，只能操作普通文本文件。最常见的文本文 件：.txt，.java，.c，.cpp 等语言的源代码。尤其注意.doc,excel,ppt这些不是文本文件。

### 4、缓冲流

提供流的读取、写入的速度

提高读写速度的原因：提供了一个缓冲区

### 5、转换流

将char转换为byte

InputStreamReader：实现将字节的输入流按指定字符集转换为字符的输入流，解码

OutputStreamWriter：实现将字符的输出流按指定字符集转换为字节的输出流，编码

### 6、标准输入、输出流

### 7、打印流

### 8、数据流

### 9、对象流

重点：序列化机制

#### 序列化和反序列化

序列化：用ObjectOutputStream类保存基本类型数据或对象的机制，内存----->文件

将内存中的java对象保存到磁盘中或者通过网络传输出去

反序列化：用ObjectInputStream类读取基本类型数据或对象的机制，文件----->内存

将磁盘中的对象数据源读出

#### Serializable接口

凡是实现Serializable接口的类都有一个表示序列化版本标识符的静态变量：

private static final long serialVersionUID; 

serialVersionUID用来表明类的不同版本间的兼容性。简言之，其目的是以序列化对象进行版本控制，有关各版本反序列化时是否兼容。如果类没有显示定义这个静态常量，它的值是Java运行时环境根据类的内部细节自动生成的。若类的实例变量做了修改，serialVersionUID 可能发生变化。故建议显式声明。

### 10、随机存取文件流

### 11、NIO.2中Path、Paths、Files类的使用

## 第14章 网络编程

![image-20211211154252672](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211211154252672.png)

#### 1、网络通信要素概述

IP和端口号 

网络通信协议

#### 2、通信要素1：IP和端口号

IP：唯一的标识 Internet 上的计算机（通信实体）

端口号：标识正在计算机上运行的进程（程序）

#### 3、通信要素2：网络协议

TCP/IP协议簇

#### 4、TCP网络编程

![image-20211211165932089](C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211211165932089.png)

```java
package WindowTest;
import com.sun.xml.internal.messaging.saaj.util.ByteOutputStream;
import org.junit.Test;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.ServerSocket;
import java.net.Socket;
import java.nio.charset.StandardCharsets;

/*
 * 实现TCP的网络编程
 * 客户端发送信息给服务端，服务端将数据显示在控制台上
 */
public class WindowTest {
    @Test
    public void client() throws IOException {
        Socket socket = null;
        OutputStream os = null;
        try {
            //1、创建Socket对象，指明服务器算的ip和端口号
            InetAddress inet=InetAddress.getByName("127.0.0.1");
            socket = new Socket(inet,8899);
            //2、获取一个输出流用于输出数据
            os = socket.getOutputStream();
            //3、写出数据的操作
            os.write("你好".getBytes(StandardCharsets.UTF_8));

        } finally {
            //4、资源的关闭
            if (os!=null){
                try {
                    os.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
            if (socket!=null){
                try {
                    socket.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }

        }

    }
    @Test
    public void server() throws IOException{
        ServerSocket ss= null;
        Socket socket= null;
        InputStream is= null;
        ByteOutputStream baos= null;
        try {
            //1、创建服务器端的ServerSocket，指明自己的端口号
            ss = new ServerSocket(8899);
            //2、调用accept方法表示接收来自客户端的socket
            socket = ss.accept();
            //3、获取输入流
            is = socket.getInputStream();
            //4、读取输入流中的数据
            baos = new ByteOutputStream();
            byte[] buffer=new byte[1024];
            int len=0;
            while ((len=is.read(buffer))!=-1){
                baos.write(buffer,0,len);
            }
            System.out.println(baos.toString());
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            //5、资源的关闭
            if (baos != null) {
                try {
                    baos.close();
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
            if (is != null) {

                try {
                    is.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }if(socket!=null){

                try {
                    socket.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }if(ss!=null){

                try {
                    ss.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
} 
```

- 客户端： 

  - 自定义 

  - 浏览器 

- 服务端：

  - 自定义 

  - Tomcat服务器

#### 5、UDP网络编程

1. UDP数据报通过数据报套接字 DatagramSocket 发送和接收，系统不保证 UDP数据报一定能够安全送到目的地，也不能确定什么时候可以抵达。
2. DatagramPacket 对象封装了UDP数据报，在数据报中包含了发送端的IP 地址和端口号以及接收端的IP地址和端口号。
3. UDP协议中每个数据报都给出了完整的地址信息，因此无须建立发送方和 接收方的连接。

#### 6、URL编程

URL(Uniform Resource Locator)：统一资源定位符，它表示 Internet 上某一资源的地址

**URI、URL和URN的区别**

1. URI，是uniform resource identifier，统一资源标识符，用来唯一的标识一个资源。
2. URL是uniform resource locator，统一资源定位符，它是一种具体的URI，即URL可以用来标识一个资源，而且还指明了如何locate这个资源。 
3. URN，uniform resource name，统一资源命名，是通过名字来标识资源， 比如mailto:java-net@java.sun.com。
4. URI是以一种抽象的，高层 次概念定义统一资源标识，而URL和URN则是具体的资源标识的方式。
5. URL 和URN都是一种URI。

## 第15章 JAVA反射机制

### 1、Java反射机制概述

java.lang.Class:代表一个类 

java.lang.reflect.Method:代表类的方法

java.lang.reflect.Field:代表类的成员变量

java.lang.reflect.Constructor:代表类的构造器

### 2、理解Class类并获取Class实例

```java
@Test
public void test2() throws Exception {
    Class clazz=Person.class;
    //1、通过反射，创建Person类的对象
    Constructor con=clazz.getConstructor(String.class,int.class);
    Object obj=con.newInstance("Tom",12);
    Person p=(Person) obj;
    //2、通过反射调用对象指定的属性、方法
    //调用属性
    Field age=clazz.getDeclaredField("age");
    age.set(p,10);
    System.out.println(p.toString());
    //调用方法
    Method show = clazz.getDeclaredMethod("show");
    show.invoke(p);
    System.out.println("**************");
    
    //通过反射，可以调用Person类的私有结构
    Constructor deC = clazz.getDeclaredConstructor(String.class);
    deC.setAccessible(true);
    Person p1 = (Person) deC.newInstance("Jerry");
    //调用私有属性
    Field name = clazz.getDeclaredField("name");
    name.setAccessible(true);
    name.set(p1,"Micheal");
    System.out.println(p1);
    //调用私有方法
    Method showNation = clazz.getDeclaredMethod("showNation", String.class);
    showNation.setAccessible(true);
    showNation.invoke(p1,"中国");
}
```

1. 直接通过new的方式或者反射的方式都可以调用公共的结构，开发中到底用哪个

   直接new，什么时候用反射，反射的特征：动态性

2. 反射机制与面向对象中的封装性是不是矛盾的？如何看待两个技术

   不矛盾

3. java.lang.Class的理解

   类的加载过程：程序经过javac.exe命令之后，会生成一个或多个字节码文件（.class）结尾，接着使用java.exe命令对某个字节码文件进行解释运行，相当于将某个字节码文件加载到内存中，此过程就称为类的加载，加载到内存中的类就称为运行时的类，也就是class的实例对应一个运行时类。加载到内存中的运行时类会缓存一定时间，在此时间之内，可以通过不同的方式来获取此运行时类。

4. 获取Class实例的方式

   ```java
   @Test
   public void test3() throws ClassNotFoundException {
       //方式1：调用运行时类的属性.class
       Class<Person> class1 = Person.class;
       System.out.println(class1);
       //方式2：通过运行时类的对象
       Person p1=new Person();
       Class class2=p1.getClass();
       //方式3：调用Class的静态方法：forName(String classPath)（用得最多）
       Class class3 = Class.forName("WindowTest.Person");
       System.out.println(class3);
   }
   ```

### 3、类的加载与ClassLoader的理解

<img src="C:\Users\86187\AppData\Roaming\Typora\typora-user-images\image-20211212162455735.png" alt="image-20211212162455735" style="zoom: 50%;" />

```java
//读取配置文件（这个代码需要掌握）
@Test
public void test4() throws Exception {
    //配置文件默认识别为当前module的src下
    Properties pros = new Properties();
    ClassLoader classLoader = ReflectionTest.class.getClassLoader();
    InputStream is = classLoader.getResourceAsStream("jdbc.properties");
    pros.load(is);

    String user = pros.getProperty("user");
    String password = pros.getProperty("password");
    System.out.println("user="+user+"password="+password);
}
```

### 4、创建运行时类的对象

需要掌握

### 5、获取运行时类的完整结构

### 6、调用运行时类的指定结构

需要掌握

### 7、反射的应用：动态代理

想要实现动态代理，需要解决的问题？

1. 如何根据加载到内存中的被代理类，动态的创建一个代理类及其对象
2. 当通过代理类的对象调用方法时，如何动态地调用被代理类中地同名方法

```java
package WindowTest;

import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
import java.lang.reflect.Proxy;

public class NewInstanceTest {
    public static void main(String[] args) {
        SuperMan superMan = new SuperMan();//被代理类的对象
        //1、创建代理类的对象，传入参数：被代理类的对象
        Human proxyInstance = (Human) ProxyFactory.getProxyInstance(superMan);
        //2、使用代理的对象调用被代理类的方法
        proxyInstance.eat("土豆");
        System.out.println(proxyInstance.getBelief());
    }
}
//代理类和被代理类需要实现同一个接口
interface Human{
    String getBelief();
    void eat(String food);
}
//被代理类
class SuperMan implements Human{

    @Override
    public String getBelief() {
        return "共产主义";
    }

    @Override
    public void eat(String food) {
        System.out.println("我喜欢吃"+food);
    }
}
//生成代理类
class ProxyFactory{
    //调用此方法返回一个代理类的对象
    public static Object getProxyInstance(Object obj){//obj:被代理类的对象
        MyInvocationHandler handler = new MyInvocationHandler();
        handler.bind(obj);
        //参数分别为：被代理类的加载器，被代理类的接口（因为代理类和被代理类需要实现同一个接口），代理类到被代理类的一个方法转换的接口
        return Proxy.newProxyInstance(obj.getClass().getClassLoader(), obj.getClass().getInterfaces(),handler);
    }
}
class MyInvocationHandler implements InvocationHandler{
    private Object obj;//被代理类，需要使用被代理类的对象赋值
    //方法功能：使用被代理类的对象赋值
    public void bind(Object obj){
        this.obj=obj;
    }
    //当通过代理类的对象调用方法时，就会自动调用如下的方法：invoke()
    //将被代理类要执行的方法的功能声明在invoke中
    //参数含义：代理类的对象，代理类的对象想要调用的方法，方法形参
    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
        Object returnValue = method.invoke(obj, args);//利用反射，调用方法的主体是被代理类的对象
        return returnValue;
    }
}
```

此时整个代码里没有代理类，也叫不出代理类的类名，代理类是通过代理类工厂自动生成的，直接得到了代理类的对象

APO

## 第16章JAVA8 的其他新特性

### 之前提到的JAVA8新特性：

#### java8中接口新特性

JDK8：除了全局常量和抽象方法，还可以定义静态方法和默认方法（default关键字修饰）

1. 接口中定义的静态方法只能通过接口来调用，接口.方法。
2. 通过实现类的对象，可以调用接口中的默认方法，对象.方法。如果实现类重写了接口中的默认方法，调用时仍然调用的是重写以后的方法
3. 如果子类（或实现类）继承的父类和实现的接口中声明了同名同参数的方法，子类在没有重写此方法的情况下调用的是父类中的方法——类优先原则
4. 如果实现类实现了多个接口，而这个多个接口中定义了同名同参数的默认方法，在实现类没有重写方法的情况下会报”接口冲突“错误，此时需要重写。
5. 如何在子类（或者实现类）调用父类、接口中被重写的方法，接口.super.方法

#### JDK8中新日期时间API

#### JDK8中注解的新特性

可重复注解、类型注解

#### HashMap JDK8

JAVA8之前是先建好数组，JAVA8之后是添加元素的时候才去造数组

### 其他新特性

![](C:\Users\86187\Desktop\offer\尚硅谷\尚硅谷JAVA基础课件笔记源码资料\新建文件夹\1_课件\第2部分：Java高级编程\尚硅谷_宋红康_第16章_Java8的其它新特性\Java 8新特性 尚硅谷-宋红康.bmp)

#### 1、Lambda表达式

```java
 (o1,o2) -> Integer. compare(o1,o2);
```

2.格式:

-> :Lambda 操作符或 箭头操作符

->左边: lambda形参列表(其实就是接口中的抽象方法的形参列表)

->右边: Lambda体 (其实就是重写的抽象方法的方法体)

Lambda表达式的本质：作为函数式接口的实例

#### 2、函数式（Functional）接口

#### 3、方法引用与构造器引用

1. 方法引用本质上就是Lambda表达式，而Lambda表达式作为函数式接口的实例，自然方法引用也是函数时接口的实例

2. 使用格式：类（或对象）：：方法名

   ​		对象：：非静态方法 P673

   ​		类：：静态方法 P674

   ​		类：：非静态方法 P675 

3. 要求：接口中的抽象方法的形参列表和返回值类型与方法医用的方法形参列表和返回值类型相同

#### 4、强大的Stream API

1、Sream关注的是对数据的运算，与CPU打交道

​	集合关注的是数据的存储，与内存打交道

2、操作流程

1- 创建 Stream 一个数据源（如：集合、数组），获取一个流 

2- 中间操作 一个中间操作链，对数据源的数据进行处理 

3- 终止操作(终端操作) 一旦执行终止操作，就执行中间操作链，并产生结果。之后，不会再被使用

3、说明

①Stream 自己不会存储元素。 

②Stream 不会改变源对象。相反，他们会返回一个持有结果的新Stream。

③Stream 操作是延迟执行的。这意味着他们会等到需要结果的时候才执行。

4、一个中间操作链，对数据源的数据进行处理

一旦执行终止操作，就执行中间操作链并产生结果，之后不会再被使用

#### 5、Optional类

## 第17章 JAVA9 & JAVA10 & JAVA11新特性





