[接Java笔记day9 >](./Java笔记day9.md)

### 学习内容
本日主要学习了JDK8新时间。
## 一、JDK8日期
## 1）JDK8日期、时间、日期时间
DK8新增的日期类分得更细致一些，比如表示年月日用LocalDate类、表示时间秒用LocalTime类、而表示年月日时分秒用LocalDateTime类等；除了这些类还提供了对时区、时间间隔进行操作的类等。它们几乎把对日期/时间的所有操作都通过了API方法，用起来特别方便
**注意：需要import java.time.LocalDate/LocalTime/LocalDateTime才能使用。**
代码示例：
- LocalDate类的基本使用
```java
package D1_jdk8_date_time;
import java.time.LocalDate;

public class Test {
    public static void main(String[] args) {
        //ローカル日付オブジェクトを獲得する
        LocalDate ld = LocalDate.now();
        System.out.println(ld);

        //日付オブジェクトの情報を獲得する
        int year = ld.getYear();
        int month = ld.getMonthValue();
        int day = ld.getDayOfMonth();
        int dayOfYear = ld.getDayOfYear();  //日
        int dayOfMonth = ld.getDayOfMonth();  //一年中の何日
        int dayOfWeek = ld.getDayOfWeek().getValue();  //何曜日
        System.out.println(year);
        System.out.println(month);
        System.out.println(day);
        System.out.println();
        System.out.println(dayOfYear);
        System.out.println(dayOfMonth);
        System.out.println(dayOfWeek);
        System.out.println();

        //直接的にある情報を直す：withYear、widthMonth、withDayOfMonth、withDayOfYear
        LocalDate ld2 = ld.withYear(2099);
        LocalDate ld3 = ld.withMonth(11);
        System.out.println(ld2);
        System.out.println(ld3);
        System.out.println(ld);
        System.out.println();

        //ある情報をxxを足す
        LocalDate ld4 = ld.plusYears(2);
        LocalDate ld5 = ld.plusMonths(10);
        LocalDate ld6 = ld.plusDays(30);
        LocalDate ld7 = ld.plusWeeks(1);
        System.out.println(ld4);
        System.out.println(ld5);
        System.out.println(ld6);
        System.out.println(ld7);
        System.out.println();

        //指定された日付のLocalDateオブジェクトを獲得する
        LocalDate ld8 = LocalDate.of(2027, 07, 01);
        System.out.println(ld8);

        //二つの日付オブジェクトはイコールかどうか、前とか後ろとかを判断する。
        System.out.println(ld8.equals(ld7));
        System.out.println(ld8.isBefore(ld7));
        System.out.println(ld8.isAfter(ld7));
    }
}
```

- LocalTime类的基本使用
```java
package D2_jdk8_localTime;
import java.time.LocalTime;

public class Test {
    public static void main(String[] args) {
        LocalTime lt = LocalTime.now();
        System.out.println(lt);

        //時間の情報を獲得する
        int hour = lt.getHour();
        int minute = lt.getMinute();
        int second = lt.getSecond();
        int nano = lt.getNano();
        System.out.print(hour+":"+minute+":"+second+":"+nano+"\n");
        System.out.println();

        //時間を直す
        LocalTime lt2 = lt.withHour(10);
        LocalTime lt3 = lt.withMinute(10);
        LocalTime lt4 = lt.withSecond(10);
        LocalTime lt5 = lt.withNano(10);
        System.out.println(lt2);
        System.out.println(lt3);
        System.out.println(lt4);
        System.out.println(lt5);
        System.out.println();

        //いくらを足す
        LocalTime lt6 = lt.plusHours(10);
        LocalTime lt7 = lt.plusMinutes(10);
        LocalTime lt8 = lt.plusSeconds(10);
        LocalTime lt9 = lt.plusNanos(10);

        //いくらを減る
        LocalTime lt10 = lt.minusHours(10);
        LocalTime lt11 = lt.minusMinutes(10);
        LocalTime lt12 = lt.minusSeconds(10);
        LocalTime lt13 = lt.minusNanos(10);

        //指定された時間のオブジェクトを獲得する
        LocalTime lt14 = LocalTime.of(12, 12, 14);
        System.out.println(lt14);
        System.out.println();

        //二つの時間オブジェクトはイコールかどうか、前とか後ろとかを判断する。
        System.out.println(lt13.equals(lt14));
        System.out.println(lt13.isAfter(lt14));
        System.out.println(lt13.isBefore(lt14));
    }
}
```

- LocalDateTime类的基本使用
```java
package D3_jdk8_localDateTime;

import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;

public class Test {
    public static void main(String[] args) {
        LocalDateTime ldt = LocalDateTime.now();
        System.out.println(ldt);

        //日付と時間の全部の情報を獲得できる
        int year = ldt.getYear();
        int month = ldt.getMonthValue();
        int day = ldt.getDayOfMonth();
        int dayOfYear = ldt.getDayOfYear();
        int dayOfWeek = ldt.getDayOfWeek().getValue();
        int hour = ldt.getHour();
        int minute = ldt.getMinute();
        int second = ldt.getSecond();
        int nano = ldt.getNano();

        //時間情報を直す
        LocalDateTime ldt2 = ldt.withYear(2027);
        LocalDateTime ldt3 = ldt.withMinute(30);

        //いくらを足す
        LocalDateTime ldt4 = ldt.plusYears(2);
        LocalDateTime ldt5 = ldt.plusMonths(3);

        //いくらを経る
        LocalDateTime ldt6 = ldt.minusDays(4);
        LocalDateTime ldt7 = ldt.minusYears(5);

        //指定された日付と時間のLocalDateTimeオブジェクトを獲得する
        LocalDateTime ldt8 = LocalDateTime.of(2027, 07, 01, 12, 12, 12, 122);

        //二つの時間オブジェクトはイコールかどうか、前とか後ろとかを判断する。
        System.out.println(ldt8.equals(ldt7));
        System.out.println(ldt8.isAfter(ldt7));
        System.out.println(ldt8.isBefore(ldt7));

        //LocalDateTimeをLocalDateとLocalTimeを転換できる
        LocalDate ld = ldt.toLocalDate();
        LocalTime lt = ldt.toLocalTime();
    }
}
```

## 2）JDK8日期（时区）
### 1. ZoneId
由于世界各个国家与地区的经度不同，各地区的时间也有所不同，因此会划分为不同的时区。每一个时区的时间也不太一样。
我们可以用ZoneId获取时区。
代码示例：
```java
	//システムディフォルトの時間帯を獲得する
	ZoneId zoneId = ZoneId.systemDefault();
	System.out.println(zoneId.getId());

	//javaがサポートしているすべての時間帯を獲得する
	System.out.println(zoneId.getAvailableZoneIds());

	//ある時間帯idをZoneIdオブジェクトをカプセル化にする
	ZoneId zoneId1 = ZoneId.of("Japan");
	System.out.println(zoneId1.getId());
```
### 2. ZoneDateTime
输出对应时区的时间。
代码示例：
```java
	//時間帯をつけている時間
	ZonedDateTime now = ZonedDateTime.now(zoneId1);
	System.out.println(now);

	//世界標準時を獲得する
	ZonedDateTime now1 = ZonedDateTime.now(Clock.systemUTC());
	System.out.println(now1);

	//システムディフォルトの時間帯のZonedDateTimeオブジェクトを獲得する
	ZonedDateTime now2 = ZonedDateTime.now();
	System.out.println(now2);
```
## 3）JDK8日期（Instant类）
通过获取Instant的对象可以拿到此刻的时间，该时间由两部分组成：从1970-01-01 00:00:00 开始走到此刻的总秒数+不够1秒的纳秒数
代码示例：
```java
package D5_JDK8_Instant;
import java.time.Instant;

public class Test {
    public static void main(String[] args) {
        //Instantオブジェクトを作成し、今の時間情報を獲得する
        Instant now = Instant.now();

        //総秒数を獲得する
        long second = now.getEpochSecond();
        System.out.println(second);

        //一秒を足りないのナノ秒数
        int nano = now.getNano();
        System.out.println(nano);
        System.out.println(now);
    }
}
```
## 4）JDK8日期（格式化器）
它可以从来对日期进行格式化和解析。它代替了原来的SimpleDateFormat类，可以使得代码更加安全。
```java
//DateTimeFormatterオブジェクトを作成する  
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy年MM月dd日 HH:mm:ss");  
  
//時間をフォーマットにさせる  
LocalDateTime ldt = LocalDateTime.now();  
System.out.println(ldt);  
  
String format = formatter.format(ldt);  
System.out.println(format);  
  
//もう一つの方案である  
String format2 = ldt.format(formatter);  
System.out.println(format2);  
  
//時間を解析する：時間の解析は一般的にLocalDateTimeが提供する解析方法を使用して解析することである。  
String dateStr = "2029年12月12日 12:12:12";  
LocalDateTime date = LocalDateTime.parse(dateStr, formatter);  
System.out.println(date);
```
## 5）Period