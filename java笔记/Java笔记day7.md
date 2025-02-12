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
## 2）static修饰成员方法
### 1. 成员方法的分类
- **类方法：** 有static修饰的成员方法，属于类
如main方法
- **实例方法：** 无static修饰的成员方法，属于对象。
如上述的Student对象。
程序实例：
```java
package D2StaticMethod;

public class Student {
    public static void printHelloWorld() {
        System.out.println("Hello World");
        System.out.println("Hello World");
    }
}
```
测试程序：
```java
package D2StaticMethod;

public class Test {
    public static void main(String[] args) {
        Student.printHelloWorld();
    }
}
```
可以直接调用另外一个类里的类方法。
但是实例方法只能由对象来调用。
代码示例：
```java
	//オブジェクト.実例方法だけ、効用できる  
	s.score = 60;  
	s.printPass();  
//        Student.printPass();　　//エラーが発生する
```
```java
    //実例方法
    public void printPass() {
        System.out.println("score: "+(score >= 60 ? "pass": "fail"));
    }
```
## 3）static修饰成员方法的应用场景
**类方法的常见应用场景：**
- 可以做工具类。
**工具类是什么？**
- 工具类中的方法都是一些类方法，每个方法都是用来完成一个功能的，工具类是给开发人员共同使用的。
- 好处是能提高代码复用；调用方便，提高了开发效率。
代码示例：
1.code接受验证码代码：
```java
package D3_util;
import java.util.Random;

public class code {
    public static String code(int length) {
        String data = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890";
        String code = "";
        Random r = new Random();
        for (int i = 0; i < length; i++) {
            int index = r.nextInt(data.length());
            code += data.charAt(index);
        }
        return code;
    }
}
```
在登录或者注册页面直接调用即可：
```java
package D3_util;  
  
public class LoginDemo {  
    public static void main(String[] args) {  
        System.out.println(code.code(4));  
        System.out.println(code.code(5));  
    }  
}
```
## 4）static的注意事项
1. 类方法中可以直接访问类的成员，不可以直接访问实例成员。
2. 示例方法中既可以直接访问类成员，也可以直接访问实例成员。
3. 实例方法中可以出现this关键字，类方法中不可以出现this关键字。
## 5）static的应用知识：代码块
