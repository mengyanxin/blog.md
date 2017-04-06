---
title: java数据类型
date: 2017-04-06 09:18:47
tags:
- mengyan
- Java
- 数据类型
categories:
- utils
---
### java数据类型
> <pre>
                      ┏数值型━┳━整数型：byte short int long
        ┏基本数据类型━━┫       ┗━浮点型：float double
        ┃             ┣字符型：char
 数据类型╋             ┗布尔型：boolean
        ┃             ┏类（class）
        ┗引用数据类型━━╋接口（interface）
                      ┗数组（array）
</pre>

### *java 八种基础数据类型；三种引用数据类型。*

##### 第一类:整数型(byte、short、int、long)
> ##### byte
> byte由1个字节8位表示，是最小的整数类型。主要用于节省内存空间关键。
> 当操作来自网络、文件或者其他IO的数据流时，byte类型特别有用。取值范围为:[-128, 127].
> ##### short
> short用16位表示，取值范围为：[- 2^15, 2^15 - 1]。short可能是最不常用的类型了。
> short类型参与运算的时候，一样被提升为int或者更高的类型。(-32768到32767)
> ##### int
> Int 32 bits, [- 2^31, 2^31 - 1].有符号的二进制补码表示的整数。(-2147483648,到2147483647共10位)
> Integer是java为int提供的封装类
> int的默认值为0，而Integer的默认值为null，即Integer可以区分出未赋值和值为0的区别，int则无法表达出未赋值的情况。
> 例如，要想表达出没有参加考试和考试成绩为0的区别，则只能使用Integer
> ##### long
> Long 64 bits， [- 2^63, 2^63 - 1,默认值为0L].当需要计算非常大的数时，如果int不足以容纳大小，可以使用long类型。
> 如果long也不够，可以使用BigInteger类。(-9223372036854775808到9223372036854775807共19位)
> 声明Long型常量后需加L  eg:  long i = 8888888888888L;

##### 第二类:文本型char
> ##### Char
16 bits, [0, 65535], [0, 2^16 -1],从'\u0000'到'\uffff'。无符号，默认值为'\u0000'。
Java使用Unicode字符集表示字符，Unicode是完全国 际化的字符集，可以表示全部人类语言中的字符。
Unicode需要16位宽，所以Java中的char类型也使用16 bit表示。当char进行加减乘除运算的时候，也被转换成int类型，必须显式转化回来。

##### 第三类:逻辑型boolean
> ##### boolean
取值只有true 或者 false， 默认为false。boolean与是否为0没有任何关系，但是可以根据想要的逻辑进行转换。

##### 第四类:浮点型(float、double)
> ##### float
使用32 bits表示，对应单精度浮点数，运行速度相比double更快，占内存更小，但是当数值非常大或者非常小的时候会变得不精确。
精度要求不高的时候可以使用float类型
声明float型常量后需加f或者声明类型；
```
float c =(float) 11.1;
float d = 11.1f;
```
> ##### double
使用64bits为表示，将浮点子面子赋给某个变量时，如果不显示在字面值后面加f或者F，则默认为double类型。
java.lang.Math中的函数都采用double类型。如果double和float都无法达到想要的精度，可以使用BigDecimal类
