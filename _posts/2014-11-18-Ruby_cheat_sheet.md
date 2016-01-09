---     
layout: post     
title:  "Ruby_cheat_sheet"     
date:   2014-11-18 01:53:00     
categories: Ruby     
---     

基础部分     

1. puts和print的区别：puts会自动换行，print不会     
2. 一切皆是对象，连普通数字也是对象     
3. 以大写字母命名的变量，会被认为是常量（修改它会有警告）,前面加`@`符号的是全局变量     
4. 【迭代子】类似于迭代器，但是却是元素本身     
    - `容器.each{ |Name| puts Name}`     
    - `容器.collcet{。。。}`  //collect表示对迭代子操作后，把结果对其赋值     
5. 数字、字符串的互相转换     
    - 对象.to_s  =》   转为string     
    - 对象.to_i   =》  转为int     
    - 对象.to_f   =》  转为float     
    - 对象.to_a   =》  转为数组。例子：`(1..9).to_a.each{ |e| puts e} `打印1-9     
    - 字符串对象.to_sym  =》  转为`符号`。（符号是特殊的字符串?`有待深究`）     
6. 字符串拼接（插值）：     
    newString = “this is a raw string plus #{ `otherObj` }”     
7.  数组：1.容量动态增长 2.类型不限制 3. `数组<<元素`代表push_back     
    - `加法`拼接数组。`减法`去掉相同元素。     
    - `include?()`方法    =》  检查是否存在元素。     
    - `first`和`last`方法  =》  返回最初和最后元素。     
    - `reverse`方法   =》  反转数组。      
8. 字符串数组:     
    - `数组.join`方法   =》  把所有元素合成一个长字符串     
    - `字符串.split`方法 =》  把字符串分割成数组     
9. 字典（hash）     
    - 字典.keys   =》  返回key数组     
    - 字典.values =》  返回value数组     
    - 字典.delet(key) =》  删除key键值的元素     
    - `字典.delet_if { |key value| value < 25 }`  =》  删除value小于25的元素       
10. 花括号`{}`和`do-end`块，本质上都是匿名函数/代码块。     

[注]`花括号`和`do-end块`是等价的，例如：     
{% highlight Ruby %}     
容器.each do |Name|     
    puts Name    
end    
{% endhighlight %}     
 
11. `单引号`和`双引号`的区别     
    - 单引号中所有字符都是`字面值`，就是无视转义字符     
    - 单引号中，不支持字符串拼接（插值）     

12. 函数     
    - 可以定义`参数`的默认值     
    - 不必指明`返回值`，函数中最后一个语句的值就是返回值。 （当然也可以写return）     

13. 一个例子：`('a'..'z').to_a.shuffle[0..7].join`功能是随机输出一个八位的字母     

