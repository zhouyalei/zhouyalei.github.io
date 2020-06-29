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
### 贪婪和非贪婪  
   属于贪婪模式的量词，也叫做**匹配优先**量词，包括:
>     “{m,n}”、“{m,}”、“?”、“*”和“+”。  
举例： 
>源字符串：aa\<div>test1\</div>bb\<div>test2\</div>cc
1. 正则：\<div>.*\</div>  
>     <div>test1</div>bb<div>test2</div> 
2. 正则：\<div>.*?\</div> 
>     <div>test1</div>
