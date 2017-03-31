---
title: Java两整形变量互换值
date: 2017-03-31 15:25:35
tags:
- Java
- mengyan
- 换位
categories:
- utils
---
### 利用第三个临时变量
> {%codeblock%}
public static void main(String[] args){
    int x=10,y=20;
    int temp = x;
    x = y;
    y=temp;
    System.out.println("x="+x+",y="+y);
}
//输出
x=20,y=10
{%endcodeblock%}

### 使用两个数的和作为中间变量
> *ps:缺点是两个数值的和可能超过类型的最大值*
> {%codeblock%}
public static void main(String[] args){
    int x=10,y=20;
    x = x + y;
    y = x - y;
    x = x - y;
    System.out.println("x="+x+",y="+y);
}
//输出
x=20,y=10
{%endcodeblock%}

### 利用位运算符(^)异或
> *原理：一个数异或同一个数两次，结果还是这个数本身*
> {%codeblock%}
public static void main(String[] args){
    int x=10,y=20;
    x = x ^ y;
    y = x ^ y;    //y=(x^y)^y,将x的值赋给y
    x = x ^ y;    //x=x^(x^y),这是的y的值为x的最初值10，x的值为(10^20)
    System.out.println("x="+x+",y="+y);
}
//输出
x=20,y=10
{%endcodeblock%}
