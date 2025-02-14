[接Java笔记day7 >](./Java笔记day7.md)
# 一、面向对象：多态
## 1）什么是多态
- 多态是**继承/实现**情况下的一种现象，表现为：对象多态、行为多态。

代码示例：
人对象：
```java
package polymorphism;

public class People {
    public void run() {
        System.out.println("people can run");
    }
}
```
老师对象：
```java
package polymorphism;

public class Teacher extends People {
    @Override
    public void run() {
        System.out.println("teacher run fast~~");
    }
}
```
学生对象：
```java
package polymorphism;

public class Student extends People {
    @Override
    public void run() {
        System.out.println("Student run fast~~");
    }
}
```
主方法：
```java
package polymorphism;

public class Test {
    public static void main(String[] args) {
        //オブジェクトのポリモーフィズム
        People p1 = new Teacher();
        p1.run();  //行為のポリモーフィズム

        People p2 = new Student();
        p2.run();
    }
}
```
其中，对象多态指的是这边的人类对象可以指向自己的两个子对象。这被称为**对象多态**；两个人类对象调用的方法也是自己子对象的重写方法。这被称为**行为多态**。
但是若我们分别定义三个名字示例变量：
```java
    public String name = "People";
    public String name = "Teacher";
    public String name = "Student";
```
再调用name，结果输出的还是People类里的name内容。
**总结：** 
 - 对于方法，编译看左边，运行看右边。
 - 对于变量，编译看左边，运行看左边。
## 2）多态的好处
- 在多态形式下，右边对象是解耦合的，更便于拓展和维护。
**解耦合 ：** 
- 在多态形式下，右边对象是解耦合的，更便于扩展和维护。
- 定义方法时，使用父类类型的形参，可以接收一切子类对象，扩展性更强，更便利。
代码示例：
```java
//メリット1:　右のオブジェクトはいつでも差し替えできて、後の業務も変更しやすいPeople p2 = new Teacher();  
p1.run()
```
## 3）多态的类型转换问题
默认不转换状态下，不能调用子类独有的功能。
所以我们可以使用强制类型转换，去解决问题：
```java
Teacher t = (Teacher) p;
```
只要与强转后的类型相同，就可以在编译阶段完成转换：
```java
        People p2 = new Teacher();
        p2.run();
//        Teacher t = (Teacher) p2;
        ((Teacher) p2).teach();
```
这样我们就能调用Teacher独有的方法了。
# 二、final、常量
## 1）final
- final关键字是最终的意思，可以修饰（类、方法、变量）
- 修饰类：该类被称为最终类，特点是不能被继承了
- 修饰方法：该方法被称为最终方法，特点是不能被重写了
- 修饰变量：该变量只能被赋值一次
代码示例：
A类：
```java
final class A {
    public void echoA() {
        System.out.println("A");
    }

    //final方法は二度と書けない
//    @Override
//    public void echoB() {
//        System.out.println("B");
//    }
}
```
B类：
```java
package d3_final;
//ここは継承できない
//public class B extends A {
//}

//必ず新しいクラスを作成する
public class B {
    final void echoB(){
        System.out.println("A");
    }
}
```
主方法：
```java
package d3_final;

public class Test {
    public static void main(String[] args) {
        final int a = 10;
        //final変数はデータが二度と変わらない
        //a++;
    }
}
```
# 三、抽象类
## 1）认识抽象类
- 在Java中有一个关键字叫：**abstract**，他就是抽象的意思，可以用它修饰类、成员方法。
- **abstract**修饰类，这个类就是抽象类；修饰方法，这个方法就是抽象方法。
基本结构：
```java
修饰符 abstract class 类名 {
	修饰符 abstract 返回值类型 方法名称（形参列表）；
}
public abstract class A {
	public abstract void test();
}
```
## 2）抽象类的注意事项、特点
- 抽象类中不一定有抽象方法，有抽象方法的类一定是抽象类。
- 类该有的成员（成员变量、方法、构造器）抽象类都可以有。
- 抽象类最主要的特点：抽象类不能创建对象，仅作为一种特殊的父类，让子类继承并实现。
- 一个类继承抽象类，必须重写完抽象类的全部抽象方法，否则这个类也必须定义成抽象类。
代码示例：
A抽象类：
```java
package d4_abstract;

public abstract class A {
    private String name;
    public static String schoolName;

    public A() {
        name = "1";
    }

    public A(String name) {
        this.name = name;
    }
    //抽象方法：必ずabstractで修飾し、方法スローガンだけであり、方法体は絶対にないにする
    public abstract void run();

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}                                                                                       
```
B子类：
```java
package d4_abstract;

class B extends A {
    String name;

    public B() {
        name = "wan";
    }

    @Override
    public void run() {
        System.out.println("running!");
    }
}
```
主方法：
```java
package d4_abstract;

public class Test {
    public static void main(String[] args) {
        //抽象クラスはオブジェクトを作成できない
//        A a = new A();

        B b1 = new B();
        b1.run();
    }
}
```
## 3）抽象类的场景和好处
- 父类知道每个子类都要做某个行为，但每个子类要做的情况不一样，父类就定义成抽象方法，交给子类去重写实现，**我们设计这样的抽象类，就是为了更好地支持多态**。
项目实战：
需求：某宠物游戏，需要管理猫，狗的数据。
猫的数据有：名字；行为是：喵喵喵地叫
狗的数据有：名字；行为是：汪汪汪地叫
请用面向对象编程设计该程序。
代码示例：
动物抽象类：
```java
package D5_abstractProject;

public abstract class Animal {
    protected String name;

    public abstract void GetName();
    public abstract void Voice();
}
```
猫子类：
```java
package D5_abstractProject;

public class Cat extends Animal {
    public Cat() {
        name = "a Cat";
    }
    public Cat(String name) {
        this.name = name;
    }
    @Override
    public void GetName() {
        System.out.println(name);
    }
    @Override
    public void Voice() {
        System.out.println("moew!");
    }
}
```
狗子类：
```java
package D5_abstractProject;

public class Dog extends Animal {
    public Dog() {
        name = "a dog";
    }
    public Dog(String name) {
        this.name = name;
    }

    @Override
    public void GetName() {
        System.out.println(name);
    }
    @Override
    public void Voice() {
        System.out.println("bark!");
    }
}
```
主方法：
```java
package D5_abstractProject;

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog("wangcai");
        Cat c = new Cat("miaomiao");

        d.GetName();
        d.Voice();
        System.out.println();
        c.GetName();
        c.Voice();
    }
}
```
上述代码中，抽象类可以管理控制猫和狗类的类方法。
## 4）抽象类的应用——模板方法设计模式
**模板方法设计模式解决了什么问题？**
- 解决方法中存在重复代码的问题。
**模板方法设计模式的写法**
1. 定义一个抽象类
2. 在里面定义2个方法
	- 一个是模板方法：把相同代码放进里面去。
	- 一个是抽象方法：具体实现交给子类完成。
代码示例：
人抽象类：
```java
package D6_abstract_template;

public abstract class People {
    public void write() {
        System.out.println("wordwordword");
        System.out.println("havehavehave");
        System.out.println(MainArticle());
        System.out.println("makemakemake");
    }
    public abstract String MainArticle();
}
```
学生子类：
```java
package D6_abstract_template;

import D5_abstractProject.Main;

public class Student extends People{
    @Override
    public String MainArticle() {
       return "getgetgetgetgetgetgetgetgetget";
    }
}
```