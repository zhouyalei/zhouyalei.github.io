![loading](../../images/reg-exp.jpeg)

>/\b([a-z]+) \1\b/gi	一个单词连续出现的位置。  
 /(\w+):\/\/([^/:]+)(:\d*)?([^# ]*)/	将一个URL解析为协议、域、端口及相对路径。  
 /^(?:Chapter|Section) [1-9][0-9]{0,1}$/	定位章节的位置。  
 /[-a-z]/	a至z共26个字母再加一个-号。  
 /ter\b/	可匹配chapter，而不能匹配terminal。  
 /\Bapt/	可匹配chapter，而不能匹配aptitude。  
 /Windows(?=95 |98 |NT )/	可匹配Windows95或Windows98或WindowsNT，当找到一个匹配后，从Windows后面开始进行下一次的检索匹配。  
 /^\s*$/	匹配空行。  
 /\d{2}-\d{5}/	验证由两位数字、一个连字符再加 5 位数字组成的 ID 号。  
 /<\s*(\S+)(\s[^>]*)?>[\s\S]*<\s*\/\1\s*>/	匹配 HTML 标记。  

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
