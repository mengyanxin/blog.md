---
title: Java进制转换方法
date: 2017-03-31 16:22:05
tags:
- mengyan
- Java
- 进制转换
categories:
- utils
---
### 方法调用及结果
> {%codeblock%}
public static void main(String[] args){
    int x = 128;
    String value;
    //十进制转成十六进制
    value = Integer.toHexString(x);
    System.out.println(value);//80
    //十进制转成八进制
    value = Integer.toOctalString(x);
    System.out.println(value);//200
    //十进制转成二进制
    value = Integer.toBinaryString(x);
    System.out.println(value);//10000000
    //十六进制转成十进制
    value = Integer.valueOf("FFFF",16).toString();
    System.out.println(value);//65535
    //八进制转成十进制
    value = Integer.valueOf("776",8).toString();
    System.out.println(value);//510
    //二进制转十进制
    value = Integer.valueOf("0101",2).toString();
    System.out.println(value);//5
}
{%endcodeblock%}
