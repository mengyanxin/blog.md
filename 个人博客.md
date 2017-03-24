---
title: Dozer进行模型转换时格式化 # 这是标题
tags:   # 这里写的标签会自动汇集到 tags 页面上
- Java # 可配置多个标签，注意格式
- Test
categories:
- go
---
## 模型转换时格式化

Dozer除了默认的模型转化，还可以通过配置map方法或者XML配置文件来进行自定义转化

例如我们要将Date类型转化为格式化后的结果
{% codeblock %}
//进行转化时配置
BeanMappingBuilder configure = new BeanMappingBuilder() {
    @Override
    protected void configure() {
        mapping(SourceObj.class, TargetObj.class, TypeMappingOptions.dateFormat("yyyy-MM-dd"));
    }
};
//创建Dozer
DozerBeanMapper dozer = new DozerBeanMapper();
//添加配置
dozer.addMapping(configure);
//进行转化
dozer.map(source, target);
{% endcodeblock %}如果在source和target中有两个日期时间，一个叫 firstDate 一个叫 secondDate 想使用不同的格式化

{% codeblock %}
@Override
protected void configure() {
  //为first配置横杠格式化
  mapping(SourceObj.class, TargetObj.class, TypeMappingOptions.dateFormat("yyyy-MM-dd")).fields("firstDate","firstDate");
  //为second配置斜杠格式化
  mapping(SourceObj.class, TargetObj.class, TypeMappingOptions.dateFormat("yyyy/MM/dd")).fields("secondDate","secondDate");
}
{% endcodeblock %}
### 与Spring注解配合使用

在HTTP中接受字符串日期想自动转化成Date类型，可以采用Spring的注解 DateTimeFormat 参考文章

在Java层返回给HTTP的Object时想把Date类型再转化成字符串类型，可以通过

* 重写GetSet方法，但是可能会无法使用Dozer工具
* 配置Dozer的BeanMappingBuilder
