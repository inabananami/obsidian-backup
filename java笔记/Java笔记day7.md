接[Java笔记day6 >](./Java笔记day6.md)

# 一、static与类
## 1）static修饰成员变量
代码示例:
```java
package D1StaticDemo;

public class Test {
    public static void main(String[] args) {
        Student.name = "初华";

        Student s1 = new Student();
        s1.name = "madongmei";

        Student s2 = new Student();
        s2.name = "madongmei2";

        //static変数はオブジェクトメンバーに共有されるものです
        System.out.println(s1.name);
        System.out.println(Student.name);

        //実例変数は各メンバーの特有のものです
        s1.age = 23;
        s1.age = 18;
        System.out.println(s1.age);
        System.out.println(s2.age);
    }
}
```
其中Student类中的成员变量如下：
```java
package D1StaticDemo;

public class Student {
    static String name;
    int age;
}
```
 所以static的成员变量数据由所有成员共享，int示例变量分别使用。
 