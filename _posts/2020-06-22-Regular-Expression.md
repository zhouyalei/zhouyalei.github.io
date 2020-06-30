![loading](../../images/reg-exp.jpeg)

>A regular expression is an object that describes a pattern of characters.Regular expressions are used to perform pattern-matching and "search-and-replace" functions on text.

+ [语法文档](https://www.runoob.com/regexp/regexp-syntax.html)
+ [线上测试](https://regex101.com/)

<center style="font-weight: 900;font-size: larger;">常用匹配</center>

* * *

| **匹配** | **公式** 
| --- | --- 
| 中文 | [\u4e00-\u9fa5] 
| 匹配双字节字符(包括汉字在内) | [^\x00-\xff]

* * *

```php
public function emailRegexTest ($email) {
    $pattern = "/^([\w]+)@([0-9a-z]+\.[a-z]{2,3}(\.[a-z]{2})?)$/i";
    if(preg_match($pattern, $email)) {
        return true;
    }else{
        return false;
    }
}

public function groupRegexTest ($string) {
    if(preg_match("/^(?'group1'[\w]+)-(?'group2'[\w]+)$/", $string,$matchs) > 0) {
        return $matchs;
    }else{
        return null;
    }
}
```
## 贪婪和非贪婪  
+ 贪婪/非贪婪匹配模式  
_贪婪_：当正则表达式中包含能接受重复的限定符时，匹配尽可能多的字符（**默认**）  
_非贪婪_：当正则表达式中包含能接受重复的限定符时，匹配尽可能少的字符，只需在重复的限定符后面加上 **?**

* * *

| **非贪婪限定符代码/语法** | **描述** 
| --- | --- 
| *? | 重复0次或更多次，但尽可能的少重复
| +? | 重复一次或更多次，但尽可能的少重复
| ?? | 重复0次或一次，但尽可能的少重复
| {n,}? | 重复n次或更多次，但尽可能的少重复
| {n,m}? | 重复n到m次，但尽可能的少重复

* * *

举例： *aa\<div>test1\</div>bb\<div>test2\</div>cc*  
1. 正则表达式：\<div>.*\</div>  
>     <div>test1</div>bb<div>test2</div>  
2. 正则表达式：\<div>.*?\</div> 
>     <div>test1</div>  

## 正则表达式的运算符优先级  
>转义符->括号和中括号->限定符->定位点和序列（字符）->替换  

## 正则表达式的常用模式  
+ 忽略大小写（i）
+ 多行模式（m）
+ 点号通配模式（s）:点号通配换行符
+ 懒惰模式（U）:相当于前面的?
+ 结尾模式（D）:匹配时限定$匹配出来的不可有换行
+ 支持UTF-8转义表达（u）:使表达式支持UTF-8  
## 正则表达式的使用注意事项
1. 使用字符组代替分支条件  
2. 优先选择最左端的匹配结果  
3. 标准量词是匹配优先的  
4. 谨慎用点号，尽可能不用*号和+号  
5. 尽量使用字符串函数处理代替  
6. 合理使用括号  
7. 起始、行描点优化  
8. 拆分大的正则表达式  
