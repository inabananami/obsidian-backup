<a href="https://github.com/inabananami/obsidian-backup/blob/main/java%E7%AC%94%E8%AE%B0/Java%E7%AC%94%E8%AE%B0day2.md">接day2笔记 ></a>
# 一、语句
## 1）分支结构
### 1. 单个if语句
```java
public class IfElse {
    public static void main(String[] args) {
        int a = 1, b = 2;
        if(a == 1) {
            System.out.println(a);
        }
    }
}
```
### 2. if...else语句
```java
public class IfElse {
    public static void main(String[] args) {
        int a = 1, b = 2;
        if(a == 0) {
            System.out.println(a);
        }
        else {
            System.out.println("error");
        }
    }
}
```
### 3. if...else if语句
```java
public class IfElse {
    public static void main(String[] args) {
        int a = 1, b = 2;
        if(a == 0) {
            System.out.println(a);
        }
        else if(b == 1) {
            System.out.println(b);
        }
    }
}
```
### 4. switch—— case语句
代码示例：
```java
public class SwitchCase {
    public static void main(String[] args) {
        int a = 1, b = 1;
        switch(a) {
            default:
                System.out.println(a);
                break;
            case 1:
                System.out.println("2");
                break;
            case 2:
                System.out.println(b);
                break;
        }
    }
}
```
其中，case语句下方一定要加break，否则这个程序中，case1和case2的语句都会被执行。
## 2）循环结构
### 1. for循环
代码示例如下：
```java
public class For {
    public static void main(String[] args) {
        for(int i = 0; i <= 10; i++) {
            System.out.printf("%d ",i);
        }
    }
}
```
程序会依次打印1—10的数字。（其中System.out.printf("%d ",i)原理与c语言一致）。
### 2. while循环
代码示例如下：
```java
public class While {
    public static void main(String[] args) {
        int a = 0;
        while(a <= 5) {
            System.out.printf("%d ",a);
            a++;
        }
    }
}
```
程序会在a<=5的条件下打印a。
### 3.do——while循环
在开发中不常使用。
代码示例如下：
```java
public class While {
    public static void main(String[] args) {
        int b = 0;
        do {
            System.out.printf("%d ", b);
            b++;
        }while(b<=5);
    }
}
```
与单while的区别是，它是先执行后判断条件。
### 4. 死循环
以下是标准的死循环，也是实际开发中常犯的错误：
**for循环篇：**
```java
	for(int i = 0;; i++) {
		System.out.println(i);
	}
```
**while篇：**
```java
Scanner scanner = new Scanner(System.in);
int flag = 1;
while(flag == 1) {
	System.out.println("1.存钱 2.取钱 3.查看余额 4.按0退出程序");
	flag = scanner.nextInt();
}
scanner.close();
```
常用于多功能程序的循环执行，不至于执行了一次就退出整个程序。
如果不在命令行中按ctrl+c或者用户自行终止，它们将永远运行下去。
### 5. 循环嵌套
```java
for(int i = 0; i < 10; i++) {
	for(int j = 0; j < 10; j++) {
		System.out.printf(arr[i][j]);
	}
}
```
常用于遍历二维数组。
## 3）终止和随机数
### 1. break与continue
一个是阻止当前循环运行，另一个是跳过此次循环，从下一个循环开始。
### 2. 随机数random
要生成随机数，我们先要引入random API：`import java.util.Random;` 
然后这么写：
 ```java
public class RandomDemo {
    public static void main(String[] args) {
        Random r = new Random();

        //0から9まで出力する
        int num = r.nextInt(10);
        System.out.println(nume);
    }
```
可以输出0-9的随机数。
如果要输出1-10的随机数，则可以：
  `int num = r.nextInt(10) + 1;`
如果是3-17的随机数，则：
 `int num = r.nextInt(15) + 3;`
  所以有以下规律：
  要输出 N - M 的随机数，则：
   `r.nextInt(M-N+1) + N`
# 四、数组
## 1）数组是什么？
是一个容器，可以存放**同类型的数据**。
代码示例：
```java
int[] arr = {20, 10, 10, 80, 60, 90};
```
## 2）数组的操作
### 1. 数组的初始化
**完整格式：**
```java
	//完全なフォーマット
	int[] arr = new int[]{12, 24, 36};
	double[] arr2 = new double[] {89.9, 78.8, 87.7};
```
**简易格式：**
```java
	//簡易化のフォーマット
	int[] age = {18, 19, 20};
```
### 2. 数组的访问
接上方代码：
```java
	System.out.println(arr[1]);
	System.out.println(arr2[1]);
	System.out.println(age[1]);
```
可以用for循环实现遍历整个数组。
### 3. 数组的修改
接上方代码：
```java
	arr[1] = 100;
	arr2[1] = 20.2;
	age[1] = 23;
	System.out.println(arr[1]);
	System.out.println(arr2[1]);
	System.out.println(age[1]);
```
现在输出的是修改后的数值。
### 4. 数组的动态初始化
先不进行赋值，只设置长度，在合适的时候进行赋值。
```java
public class ArrayDynamicInitialize {
    public static void main(String[] args) {
        //ダイナミックな初期化
        int[] arr = new int[3];
        for(int i = 0; i < arr.length; i++) {
            arr[i] = i + 1;
            System.out.printf("%d ", arr[i]);
        }
    }
}
```
比c语言malloc动态管理内存要简单。特别是初始化一个动态二位数组。