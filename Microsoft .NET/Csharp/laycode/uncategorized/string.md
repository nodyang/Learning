# C# string

## 取文本中间

```c#
var curdir0 = "a1a".GetStringMidFromEnd1("a", "a");
var curdir1 = "/1/".GetStringMidFromEnd1("/", "/");
var curdir2 = @"123456".GetStringMidFromEnd1(@"2", @"56");
var curdir3 = @"iloveseo".GetStringMidFromEnd1(@"lo", @"seo");
```

```c#
        /// <summary>
        /// 取文本中间
        /// </summary>
        /// <param name="allStr">原字符</param>
        /// <param name="firstStr">前面的文本</param>
        /// <param name="lastStr">后面的文本</param>
        /// <returns>返回获取的值</returns>
        public static string GetStringMid(string str, string str1, string str2)
        {
            int leftlocation;//左边位置
            int rightlocation;//右边位置
            int strmidlength; ;//中间字符串长度
            string strmid;//中间字符串
            leftlocation = str.IndexOf(str1);
            //获取左边字符串头所在位置
            if (leftlocation == -1)//判断左边字符串是否存在于总字符串中
            {
                return "";
            }
            leftlocation = leftlocation + str1.Length;//获取左边字符串尾所在位置
            rightlocation = str.IndexOf(str2, leftlocation);
            //获取右边字符串头所在位置
            if (rightlocation == -1 || leftlocation > rightlocation)//判断右边字符串是否存在于总字符串中，左边字符串位置是否在右边字符串前
            {
                return "";
            }
            strmidlength = rightlocation - leftlocation;//计算中间字符串长度
            strmid = str.Substring(leftlocation, strmidlength);//取出中间字符串
            return strmid;//返回中间字符串
        }
```

## WIKi

- [C#：替换字符串（文字），仅替换第 1 次出现的 - 鞠勇鸿的技术专栏 - CSDN 博客](https://blog.csdn.net/jyh_jack/article/details/86505579)
- [Replace first occurrence of pattern in a string](https://stackoverflow.com/questions/8809354/replace-first-occurrence-of-pattern-in-a-string)
- [C# 过滤特殊字符，保留中文，字母，数字，和- - 土豆爸爸 2016 - 博客园](https://www.cnblogs.com/wohexiaocai/p/9283309.html)

## 替换字符串 仅替换第 1 次出现的

```c#
string s = "aaa";
Regex r = new Regex("a");
s=r.Replace(s,"b",1);
```
