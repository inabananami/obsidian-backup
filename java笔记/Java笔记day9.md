[接Java笔记day8 >](./Java笔记day8.md)

# 一、常用API
## 1）StringBuilder类
StringBuilder代表可变字符串对象，相当于一个容器，它里面的字符串是可以改变的。
好处是比String更适合用来改变字符串，效率更高，代码更加简洁。
代码示例：
```java
package D1_StringBuilder;

public class Test {
    public static void main(String[] args) {
        StringBuilder sbuilder = new StringBuilder("みんなが叶える物語");
        StringBuilder sb2 = new StringBuilder("るてしきす");

        //内容を繋ぎ合わせる
        sbuilder.append("、君も一員で、");
        sbuilder.append("No.10だ。");
        System.out.println(sbuilder);

        //stringを反転する
        sb2.reverse();
        System.out.println(sb2);

        //stringの長さを出力する
        System.out.println(sb2.length());

        //StringBuilderはStringへ転換できる
        String s = new String();
        s = sbuilder.toString();
        System.out.println(s);
    }
}
```
## 2）StringJoiner类
StringJoiner号称是拼接神器，不仅效率高，而且代码还简洁。
代码示例：
```java
package D2_StringJoiner;

import java.util.StringJoiner;

public class Test {
    public static void main(String[] args) {
        //空白で間隔にする
        StringJoiner sj = new StringJoiner("  ");
        sj.add("ヒ");
        sj.add("ト");
        sj.add("リ");
        sj.add("ダ");
        sj.add("ケ");
        sj.add("ナ");
        sj.add("ン");
        sj.add("テ");
        sj.add("エ");
        sj.add("ラ");
        sj.add("べ");
        sj.add("ナ");
        sj.add("イ");
        sj.add("ヨ");
        sj.add("ー");
        sj.add("ー");
        System.out.println(sj);

        //参数1:　間隔符号
        //参数2:　始め
        //参数3:　結末
        StringJoiner sj2 = new StringJoiner(", ","[","]");
        sj2.add("ミューズ");
        sj2.add("アクア");
        sj2.add("虹ヶ咲スクールアイドル同好会");
        sj2.add("リェラ");
        sj2.add("蓮ノ空女学院スクールアイドルクラブ");
        System.out.println(sj2);
    }
}
```
## 3）Math类
Math是数学的意思，同js中的math方法，该类提供了许多数学运算方法，如求绝对值，求最大值，四舍五入。
代码示例：
```java
package D3_math;

public class Test {
    public static void main(String[] args) {
        //絶対値を取る
        System.out.println(Math.abs(-11));
        System.out.println(Math.abs(146));
        System.out.println(Math.abs(-3.1415));

        //上を向けて整数を取る
        System.out.println(Math.ceil(2.2));
        System.out.println(Math.ceil(146.7));

        //下を向けて整数を取る
        System.out.println(Math.floor(2.2));
        System.out.println(Math.floor(146.7));

        //四捨五入する
        System.out.println(Math.round(4.5));
        System.out.println(Math.round(146.4));

        //最大値と最小値を取る
        System.out.println(Math.max(146, 147));
        System.out.println(Math.min(227, 228));

        //ｎのｍ乗を取る
        System.out.println(Math.pow(2, 3));
        System.out.println(Math.pow(2, 10));

        //ランダム数を取る
        System.out.println(Math.random());
    }
}
```
## 4）System类
这是系统类，提供了一些获取系统数据的方法。比如获取系统时间。
代码示例：
 ```java
 package D4_System;

import java.util.StringJoiner;

public class Test {
    public static void main(String[] args) {
        //JVMを中止する(推薦しない)
//        System.exit(0);

        //今のシステム時間を獲得する(ミリ秒を獲得し、1970-1-1 0:0:0から今までの総ミリ秒である。)
        long time = System.currentTimeMillis();
        System.out.println(time);

        for (int i = 0; i < 10000000; i++) {
            System.out.print(i);
        }

        long time2 = System.currentTimeMillis();
        System.out.println("上記のforループが"+(time2-time)+"msをかかった。");
    }
}
```
## 5）Runtime类
这个类可以用来获取JVM的一些信息，也可以用这个类去执行其他的程序
代码示例：
```java
package D5_Runtime;

public class Test {
    public static void main(String[] args) {
        //今のJavaアプリとリンクしている実行オブジェクトを返す
        Runtime runtime = Runtime.getRuntime();
        System.out.println(runtime);

        //仮想マシンを中止する（０ではなければ、異常な中止です）
        //runtime.exit(0);

        //仮想マシンが使用できるCPU数を獲得する
        System.out.println(runtime.availableProcessors());
        
        //JVMのメモリー総量を返す
        System.out.println(runtime.totalMemory()/1024.0/1024.0 + "MB");

        //JVMの使用できるメモリーを返す
        System.out.println(runtime.freeMemory()/1024/1024 + "MB");
    }
}
```
## 6）BigDecimal类
BigDecimal主要可以用来进行精确的浮点数运算。**注意：需要import java.math.BigDecimal才可以进行操作。**
```java
package D6_BigDecimal;
import java.math.BigDecimal;

public class Test {
    public static void main(String[] args) {
        //BigDecimalを使って精確計算方法を身につく
        double a = 0.1;
        double b = 0.2;

        //お先にdouble型データをBigDemicalオブジェクトにして、計算を参加する
        BigDecimal a1 = new BigDecimal(a);
        BigDecimal b1 = new BigDecimal(b);

        //足す
        BigDecimal c1 = a1.add(b1);
        System.out.println(c1);

        //減る
        BigDecimal c2 = a1.subtract(b1);
        System.out.println(c2);

        //かける
        BigDecimal c3 = a1.multiply(b1);
        System.out.println(c3);

        //割り
        BigDecimal c4 = a1.divide(b1);
        System.out.println(c4);

        //割り、何位まで精確にする
        BigDecimal c5 = BigDecimal.valueOf(11.1);
        BigDecimal c6 = BigDecimal.valueOf(1.1);
        BigDecimal c7 = c5.divide(c6, 3, BigDecimal.ROUND_HALF_UP);
        System.out.println(c7);

        //BigDecimalオブジェクトをdoubleに転換する
        double db1 = c5.doubleValue();
        double db2 = c6.doubleValue();
        print(db1);
        print(db2);
    }
    public static void print(double a) {
        System.out.println(a);
    }
}
```
## 7）Date类
Java中是由这个类的对象用来表示日期或者时间。Date对象记录的时间是用毫秒值来表示的。Java语言规定，1970年1月1日0时0分0秒认为是时间的起点，此时记作0，那么1000（1秒=1000毫秒）就表示1970年1月1日0时0分1秒。**注意：需要导入import java.util.Date来输出日期**
代码示例：
```java
package D7_Date;
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        //dateオブジェクトを作成して、現在のシステム時間を代表するものだ。
        Date date = new Date();
        System.out.println(date);

        //時間のミリ秒を獲得する
        long time = date.getTime();
        System.out.println(time);

        //時間のミリ秒値を日付オブジェクトに転換：2s後の時間はどう？
        time += 2 * 1000;
        Date date2 = new Date(time);
        System.out.println(date2);

        //直接に日付オブジェクトの時間をsetTime方法に通じて直す
        Date date3 = new Date();
        date3.setTime(time);
        System.out.println(date3);
    }
}
```
## 8）SimpleDateFormat类
 把Date对象转换为指定格式的日期字符串这个操作，叫做**日期格式化**。反过来把指定格式的日期字符串转换为Date对象的操作，叫做**日期解析**。
 <table width="500px">
	 <thead>
		<tr>
			<th>字母</th>
			<th>表示含义</th>
		</tr>
	 </thead>
	 <tbody>
		 <tr>
			 <td>yyyy</td>
			 <td>年</td>
		 </tr>
		 <tr>
			 <td>MM</td>
			 <td>月</td>
		 </tr>
		 <tr>
			 <td>dd</td>
			 <td>日</td>
		 </tr>
		 <tr>
			 <td>HH</td>
			 <td>时</td>
		 </tr>
		 <tr>
			 <td>mm</td>
			 <td>分</td>
		 </tr>
		 <tr>
			 <td>ss</td>
			 <td>秒</td>
		 </tr>
		 <tr>
			 <td>SSS</td>
			 <td>毫秒</td>
		 </tr>
	 </tbody>
 </table>
例如2022年12月12日，格式是“yyyy年MM月dd日”
2022-12-12 12:12:12，格式是“yyyy-MM-dd HH:mm:ss”
上述格式可以任意拼接，但是字母不能写错。

代码示例：
```java
package D8_SimpleDateFormat;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        Date date = new Date();
        System.out.println(date);

        long time = date.getTime();
        System.out.println(time);

        //DateからSimpleDateFormatまで転換する
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        String rs = sdf.format(date);
        String rs2 = sdf.format(time);
        System.out.println(rs);
        System.out.println(rs2);
        System.out.println("-----------------------------------------------------------");

        //SimpleDateFormatからDateまで転換する
        String dateStr = "2022-12-12 12:12:11";
        SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        Date date2 = null;

        //エラーが発生させないため、try--catchで包むべきだ
        try {
            date2 = sdf2.parse(dateStr);
        } catch (ParseException e) {
            throw new RuntimeException(e);
        }
        System.out.println(date2);
    }
}
```
## 9）SimpleDateFormat案例
秒杀案例。
代码如下：
```java
package D9_TimeProject;  
import java.sql.SQLOutput;  
import java.text.ParseException;  
import java.text.SimpleDateFormat;  
import java.util.Date;  
  
public class Test {  
    public static void main(String[] args) throws ParseException {  
        String start = "2024年11月11日 0:0:0";  
        String end = "2024年11月11日 0:10:0";  
        String xj = "2024年11月11日 0:01:18";  
        String xp = "2024年11月11日 0:10:51";  
  
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");  
        Date startDate = sdf.parse(start);  
        Date endDate = sdf.parse(end);  
        Date xjDate = sdf.parse(xj);  
        Date xpDate = sdf.parse(xp);  
  
        if(!xjDate.after(endDate) && !xjDate.before(startDate)) {  
            System.out.println("小贾抢到了");  
        }  
        else {  
            System.out.println("小贾没抢到");  
        }  
        if(!xpDate.after(endDate) && !xpDate.before(startDate)) {  
            System.out.println("小皮抢到了");  
        }  
        else {  
            System.out.println("小皮没抢到");  
        }  
    }  
}
```
## 10）Calendar类
### 为什么要学习Calender？
- 若需求是将2024年09月10日增加一个月，那么Calender能比Date更加简便地增加月份。
**注意：需要导入java.util.Calendar才能使用。**
代码示例：
```java
package D10_Calender;

import java.util.Calendar;
import java.util.Date;

public class Test {
    public static void main(String[] args) {
        //システムの時間に対する日付オブジェクトを獲得する
        Calendar now = Calendar.getInstance();
        System.out.println(now);
        System.out.println();

        //日付のある情報を獲得する
        int year = now.get(Calendar.YEAR);
        System.out.println(year);
        int month = now.get(Calendar.MONTH);
        System.out.println(month);
        int dayOfMonth = now.get(Calendar.DAY_OF_MONTH);
        System.out.println(dayOfMonth);
        System.out.println();

        //Dateオブジェクトを獲得する
        Date d = now.getTime();
        System.out.println(d);
        System.out.println();

        //時間のミリ秒データを獲得する
        long time = now.getTimeInMillis();
        System.out.println(time);
        System.out.println();

        //Calenderのある情報を直す(Calender.MONTHの実際データは、０から始まるものだ)
        now.set(Calendar.MONTH, 3);
        System.out.println(now.get(Calendar.MONTH));
        System.out.println();

        //Calenderのある情報を足す、割る
        System.out.println(now.get(Calendar.DAY_OF_YEAR));
        now.add(Calendar.DAY_OF_YEAR, 100);
        System.out.println(now.get(Calendar.DAY_OF_YEAR));
        now.add(Calendar.DAY_OF_YEAR, -100);
        System.out.println(now.get(Calendar.DAY_OF_YEAR));
    }
}
```