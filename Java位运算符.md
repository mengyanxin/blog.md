---
title: Java位运算符
date: 2017-03-31 16:08:47
tags:
- mengyan
- Java
- 位运算符
categories:
- utils
---
**
位运算符主要针对二进制数的位进行逻辑运算，主要包括：与(&)、或(|)、非(~)、异或(^)
**
* 最高位为0代表正数，最高位为1的代表负数
* 原码就是符号位加上真值的绝对值，即用第一位表示符号, 其余位表示值;
* 正数的反码 = 补码 = 原码
* 负数的反码是在其原码的基础上,符号位不变，其余各个位取反;
* 负数的补码=在其原码的基础上,符号位不变, 其余各位取反, 最后+1.(即在反码的基础上+1)
* 已知一个数的补码，求原码的操作分两种情况：
    1. 如果补码的符号位为“0”，表示是一个正数，所以补码就是该数的原码。
    2. 如果补码的符号位为“1”，表示是一个负数，求原码的操作可以是：符号位为1，其余各位取反，然后再整个数加1。

### 与运算符(&)
> ##### 正数和正数
> 两个操作数中位都为1，结果才为1，否则结果为0。
> {%codeblock%}
public static void main(String[] args){
    int x=129;
    System.out.println(Integer.toBinaryString(x));//10000001
    int y=128;
    System.out.println(Integer.toBinaryString(y));//10000000
    System.out.println("x&y="+(x&y));//x&y=128
}
{%endcodeblock%}
> ##### 正数和负数
> {%codeblock%}
public static void main(String[] args){
    int x=5;
    System.out.println(Integer.toBinaryString(x));
    int y=-3;
    System.out.println(Integer.toBinaryString(y));
    System.out.println("x&y="+(x&y));//x&y=5
}
{%endcodeblock%}
**
计算流程：
**
5的二进制形式为： 0000 0101，（补码）
-3的二进制形式为：1111 1101，（按位取反+1） （计算机是以补码的形式存储，用补码计算）
计算结果为：      0000 0101 （正数，结果转化为原码 = 5）
-5的二进制形式为：1111 1011，
-3的二进制形式为：1111 1101，（按位取反+1） （计算机是以补码的形式存储，用补码计算）
计算结果为：      1111 1001 （负数，结果转化为原码 （符号位不变，按位取反+1）1000 0111 = -7）

### 或运算符(|)
> 两个位只要有一个为1，那么结果就是1，否则就为0。
> {%codeblock%}
public static void main(String[] args){
    int x=129;
    System.out.println(Integer.toBinaryString(x));//10000001
    int y=128;
    System.out.println(Integer.toBinaryString(y));//10000000
    System.out.println("x|y="+(x|y));//x|y=129
}
{%endcodeblock%}

### 非运算符(~)
> 如果位为0，结果是1，如果位为1，结果是0。
> {%codeblock%}
public static void main(String[] args){
    int x = 5;
    System.out.println(Integer.toBinaryString(x));//101
    System.out.println("~x="+(~x));//~x=-6
    int y = -5;
    System.out.println(Integer.toBinaryString(y));//11111111111111111111111111111011
    System.out.println("~y="+(~y));//~y=4
}
{%endcodeblock%}
> **计算原理：**
> 5 转化为二进制是 0000 0101，~运算规则是按位取反，那么为 1111 1010，
> 此时仍为补码，是计算机系统的存储模式，我们需要的结果是需要将补码化为原码，
> 换算过程：按位取反10000101 再整个+1，故原码为1000 0110 = -6（最高位为负，二进制转化为十进制为6）

### 异或运算符(^)
> 两个操作数的位中，相同则结果为0，不同则结果为1。
> {%codeblock%}
public static void main(String[] args){
    int x = 15;
    int y = 2;
    System.out.println("x^y="+(a^b));//x^y=13
}
{%endcodeblock%}
> *分析上面的程序段：*
a 的值是15，转换成二进制为1111，而b 的值是2，转换成二进制为0010，
根据异或的运算规律，可以得出其结果为1101 即13。

### 位移运算符(>>、<<)
> << (左移) 左移就是向左移位，如果要移动2位那么前面删掉2个0最后面补2个0
*（注意：前面删两个0只能是在0的前面没有1的地方才可以删）*
{%codeblock%}
public static void main(String[] args){
    int x = 3;
    System.out.println(x<<2);//12
    System.out.println(x>>2);//0
    int y = -3;
    System.out.println(y<<2);//-12
    System.out.println(y>>2);//-1
}
{%endcodeblock%}
一个数m左移n位，结果为m乘以2的n次方
一个数m右移n位，结果为m除以2的n次方
