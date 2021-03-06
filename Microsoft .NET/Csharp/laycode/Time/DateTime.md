# C# Time

- [C# DateTime 日期格式化](https://www.cnblogs.com/arxive/p/6415312.html)
- [C# TimeSpan 计算时间差(时间间隔)](https://www.cnblogs.com/999c/p/6170501.html)
- [C# .Net 计算函数执行的时间](https://www.cnblogs.com/sntetwt/p/4612992.html)
- [C#获取当前时区 - zhlinos 的博客 - CSDN 博客](https://blog.csdn.net/m0_37521785/article/details/79789058)
- [C# 获取系统时间及时间格式 - xjtrab - 博客园](https://www.cnblogs.com/xjtrab/articles/1878353.html)

## 时间对比

```c#
DateTime dt1 = DateTime.Now.AddDays(-16); ;

DateTime dt2 = DateTime.Now.AddDays(-15); ;

if (dt1 >= dt2)
{
    Console.WriteLine(dt1);
    Console.WriteLine(dt2);
    Console.WriteLine("未锁定");
}
else
{
    Console.WriteLine(dt1);
    Console.WriteLine(dt2);
    Console.WriteLine("已锁定");

}
if (item.Createtime >= DateTime.Now.AddDays(-15))
{

}
```

## 相关代码

```c#
DateTime.Now.ToString("yyyy-MM-dd HH:mm:ss:ffff"); // => 2016-05-09 13:09:55:2350
DateTime.Now.ToString("yyyy/MM/dd HH:mm:ss:ffff"); // => 2016/05/09 13:09:55:2350
DateTime.Now.ToString("yyyy/MM/dd HH:mm:ss:ffff dddd"); // => 2016/05/09 13:09:55:2350 星期一
// yyyy-MM-dd HH:mm:ss.ffff
DateTime.Now.ToString("yyyy-MM-dd HH:mm:ss");

// DateTime格式化的时候，z代表时区
DateTime.Now.ToString("%z")
// 结果为 +8

"yyyy-MM-ddTHH:mm:ssz" => 2018-02-03T23:33:33+8
"yyyy-MM-ddTHH:mm:sszz" => 2018-02-03T23:33:33+08
"yyyy-MM-ddTHH:mm:sszzz" => 2018-02-03T23:33:33+08:00

DateTime.Now.ToString("yyyy-MM-dd-HH-mm-ss-ffff");

```

```text
符号　　　　　　语法　　示例(2016-05-09 13:09:55:2350) 格式说明
y DateTime.Now.ToString() 2016/5/9 13:09:55 短日期 长时间
d DateTime.Now.ToString("d") 2016/5/9 短日期
D DateTime.Now.ToString("D") 2016年5月9日 长日期
f DateTime.Now.ToString("f") 2016年5月9日 13:09 长日期 短时间
F DateTime.Now.ToString("F") 2016年5月9日 13:09:55 长日期 长时间
g DateTime.Now.ToString("g") 2016/5/9 13:09 短日期 短时间
G DateTime.Now.ToString("G") 2016/5/9 13:09:55 短日期 长时间
t DateTime.Now.ToString("t") 13:09 短时间
T DateTime.Now.ToString("T") 13:09:55 长时间
u DateTime.Now.ToString("u") 2016-05-09 13:09:55Z
U DateTime.Now.ToString("U") 2016年5月9日 5:09:55本初子午线的长日期和长时间
m DateTime.Now.ToString("m") 5月9日
M DateTime.Now.ToString("M") 5月9日
r DateTime.Now.ToString("r") Mon, 09 May 2016 13:09:55 GMT
R DateTime.Now.ToString("R") Mon, 09 May 2016 13:09:55 GMT
y DateTime.Now.ToString("y") 2016年5月
Y DateTime.Now.ToString("Y") 2016年5月
o DateTime.Now.ToString("o") 2016-05-09T13:09:55.2350000
O DateTime.Now.ToString("O") 2016-05-09T13:09:55.2350000
s DateTime.Now.ToString("s") 2016-05-09T13:09:55
```

## 计算函数执行的时间

```c#
protected void StopwatchTest()
{
    System.Diagnostics.Stopwatch stopwatch = new System.Diagnostics.Stopwatch();
    stopwatch.Start(); //  开始监视代码
    //_________________要执行的函数______________________
    //Code……
    stopwatch.Stop(); //  停止监视
    TimeSpan timeSpan = stopwatch.Elapsed; //  获取总时间
    double hours = timeSpan.TotalHours; // 小时
    double minutes = timeSpan.TotalMinutes;  // 分钟
    double seconds = timeSpan.TotalSeconds;  //  秒数
    double milliseconds = timeSpan.TotalMilliseconds;  //  毫秒数
}
```

## 下表列出了可被合并以构造自定义模式的模式。这些模式是区分大小写的

```C#
  d 月中的某一天。一位数的日期没有前导零。
　dd 月中的某一天。一位数的日期有一个前导零。
　ddd 周中某天的缩写名称，在 AbbreviatedDayNames 中定义。
　dddd 周中某天的完整名称，在 DayNames 中定义。
　M 月份数字。一位数的月份没有前导零。
　MM 月份数字。一位数的月份有一个前导零。
　MMM 月份的缩写名称，在 AbbreviatedMonthNames 中定义。
　MMMM 月份的完整名称，在 MonthNames 中定义。
　y 不包含纪元的年份。如果不包含纪元的年份小于 10，则显示不具有前导零的年份。
　yy 不包含纪元的年份。如果不包含纪元的年份小于 10，则显示具有前导零的年份。
　yyyy 包括纪元的四位数的年份。
　gg 时期或纪元。如果要设置格式的日期不具有关联的时期或纪元字符串，则忽略该模式。

  h 12 小时制的小时。一位数的小时数没有前导零。
　hh 12 小时制的小时。一位数的小时数有前导零。
　H 24 小时制的小时。一位数的小时数没有前导零。
　HH 24 小时制的小时。一位数的小时数有前导零。
```
