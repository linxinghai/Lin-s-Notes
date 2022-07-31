#runoob

正则表达式

语法

修饰符

元字符

运算符的优先级

匹配规则

示例
```JavaScript
var str = "abc123-_def";
var patt = /[a-zA-Z0-9_-]+/;
document.write(str.match(patt));
```