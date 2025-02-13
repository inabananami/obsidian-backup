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
