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
