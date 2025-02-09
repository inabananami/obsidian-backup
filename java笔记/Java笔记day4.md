[接java笔记day3 >](./Java笔记day3.md)
# 一、方法
## 1）方法概述
方法的定义与运用如下：
```java
public class MethodDemo1 {
    public static int Plus(int i, int j) {
        return i + j;
    }
    public static void main(String[] args) {
        int i = 4, j = 1;
        System.out.println(Plus(i, j));
    }
}
```
## 2）方法定义的注意事项
- 方法可以放在主方法前面和后面，但一个方法不能定义在另一个方法里面。
- 若上述方法为void，则不能返回任何数据。
- return语句相当于break，下面的语句不会执行。
- 调用有返回值的方法，我们可以：
1. 用变量接收结果
2. 直接输出调用
3. 可以直接调用
- 调用无返回值的方法，我们只能直接调用（因为相应功能已经完全）。
## 3）方法案例
### 1. 案例1：计算1 ~ n的和
代码如下：
```java
package project.src;

public class SumOfOneToN {
    public static int Sum(int end) {
        int sum = 0;
        for(int i = 1; i <= end; i++) {
            sum += i;
        }
        return sum;
    }
    public static void main(String[] args) {
        int n = 100;
        int sum = Sum(n);
        System.out.println(sum); 
    }
}
```
### 2. 案例2：判断一个数是奇数还是偶数
代码如下：
```java
package project.src;

public class NumberJudge {
    public static void Judge(int num) {
        if(num == 0) {
            System.out.println(num+" 是偶数");
        }
        else if(num % 2 == 0) {
            System.out.println(num+" 是偶数");
        }
        else {
            System.out.println(num+" 是奇数");
        }
    }
    public static void main(String[] args) {
        int n = 137;
        Judge(n);
    }
}
```
## 4）方法在计算机的原理
方法被调用的时候，是进入到**栈内存**中运行。
方法在栈中执行完毕后，有返回值的把返回值传给栈底的**main函数**，然后出栈。
## 5）方法参数传递
代码示例：
此处的a只是**数值**。
```java
public class MethodDemo2 {
    public static void change(int a) {
        System.out.println(a);
        //このaは局部的な変数です
        a = 20;
        System.out.println(a);
    }
    public static void main(String[] args) {
        int a = 10;
        change(a);
        //なので、このaはmain方法のaになったり、出力は10 20 10になったりします。
        System.out.println(a);
    }
```
代码示例：
通过c语言，我们得知**数组的本质是指针**。所以所有方法在操作数组的数据的时候，改变的是数组指向的内存地址。
```java
    public static void change2(int[] arr) {
        System.out.println(arr[1]);
        arr[1] = 333;
        System.out.println(arr[1]);
    }
    public static void main(String[] args) {
        int[] arr = new int[]{1,2,4};
        change2(arr);
        System.out.println(arr[1]);
    }
}
```
所以这种情况输出是2 333 333 。
## 6）方法参数传递案例
**需求：**
- 输出一个int类型的数组内容，要求输出格式为：\[11,22,33,44,55\]。
代码示例：
```java
package project.src;

public class ArrayOutput {
    public static void ArrayOut(int[] arr) {
        String text = "[";
        for(int i = 0; i < arr.length; i++) {
            if(i == arr.length - 1) {
                text += arr[i];
                break;
            }
            text += arr[i];
            text += ", ";
        }
        text += "]";
        System.out.println(text);
    }
    public static void main(String[] args) {
        int[] arr = {23,24,25,26,27};
        ArrayOut(arr);
    }
}
```
 使用字符串输出，可以拼接字符串，实现需求中的打印格式。
## 7）方法重载
同C++，Java的方法重载原理也一样。
代码示例：
```java
public class MethodDemo3 {
    public static int IntPlus(int a, int b) {
        return a + b;
    }
    public static int IntPlus(int a, int b, int c) {
        return a + b + c;
    }
    public static void main(String[] args) {
        int a = 10,b = 10, c = 10;
        System.out.println(IntPlus(a, b));
        System.out.println(IntPlus(a, b, c));
    }
}
```
通过形参的数量，形参的类型来重载函数。
**注意：不同返回值但是形参数量种类都相同的，不构成重载标准！**
# 二、项目
## 1）输出九九乘法表和三角形
### 1. 输出九九乘法表
代码如下：
```java
public class NineNineTable {
    public static void main(String[] args) {
        for(int i = 1; i <= 9; i++) {
            for(int j = 1; j <= i; j++) {
                System.out.print(j + "x"+ i +"="+ j * i+"\t");
            }
            System.out.println();
        }
    }
}
```
### 2. 输出奇数的三角形
代码如下：
```java
public class Triangle_2 {
    public static void main(String[] args) {
        for(int i = 0; i < 5; i++) {
            for(int k = 5 - i; k >= 0; k-- ) {
                System.err.print(" ");
            }
            for(int j = 1; j <= 2 * i + 1; j++) {
                System.err.print("*");
            }
            System.out.println();
        }
    }
}
```
### 3. 输出偶数的三角形
代码如下：
```java
public class Triangle_1 {
    public static void main(String[] args) {
        for(int i = 0; i  < 6; i++) {
            for(int k = 6 - i; k >= 0; k-- ) {
                System.err.print(" ");
            }
            for(int j = 0; j <= i; j++) {
                System.out.print(" * ");
            }
            System.out.println();
        }
    }
}
```
## 2）买飞机票
需求：用户购买机票时，机票原价会按照淡季、旺季，头等舱还是经济舱的情况进行相应的优惠，优惠方案如下：5-10月为旺季，头等舱9折，经济舱8.5折；11月到来年4月为淡季，头等舱7折，经济舱6.5折，请开发程序计算出用户当前机票的优惠价。
代码如下：
```java
import java.util.Scanner;

public class FlightTicket {
    public static void main(String[] args) {
        int level;
        double price;
        int month = 0;
        Scanner scanner = new Scanner(System.in);
        System.out.println("please input your price of the flight ticket: ");
        price = scanner.nextDouble();
        System.out.println("please input your level of the flight, 0 is economy; 1 is premium");
        level = scanner.nextInt();
        System.out.println("please input the month you buy: ");
        month = scanner.nextInt();
        while(level != 1 && level != 0) {
            System.out.println("error occured! please input the level again: ");
            level = scanner.nextInt();
        }
        while (month >12 && month < 0) {
            System.out.println("error occured! please input the month again: ");
            month = scanner.nextInt();
        }
        if(month >= 5 && month <=10) {
            if(level == 0) {
                System.out.printf("the price of your economy flight ticket is: %.2f\n", price * 0.85);
            }
            else if(level == 1) {
                System.out.printf("the price of your premium flight ticket is: %.2f\n", price * 0.9);
            }
        }
        else {
            if(level == 0) {
                System.out.printf("the price of your economy flight ticket is: %.2f\n", price * 0.65);
            }
            else if(level == 1) {
                System.out.printf("the price of your premium flight ticket is: %.2f\n", price * 0.7);
            }
        }
        scanner.close();
    }
}
```
## 3）找素数
需求：判断101-200之间有多少个素数，并输出所有素数。
 ```java
 public class FindNumber {
    public static void main(String[] args) {
        for(int i = 101; i <= 200; i++) {
            boolean flag = true;
            for(int j = 2; j <= i / 2; j++) {
                if(i % j == 0) {
                    flag = false;
                    break;
                }
            }
            if(flag) {
                System.out.println(i+" is the number.");
            }
        }
    }
}
```
 **原理说明：** 遍历101-200的每一个数，若这个数前面一半的数有一个可以整除，就说明不是素数，则令flag为false。反之则为素数。当flag为true时，则输出这个数。