\mainmatter

# 正则表达式 {#regexp}

正则表达式是对字符串类型数据进行匹配判断，提取等操作的一套逻辑公式。可以看做是一整套约定俗成的黑话，对特定符号的约定俗成。当然，正则表达式可以广泛被采纳，是因为其背后有一套完备的公理体系。正则表达式是独立于编程语言之外的一个迷你语法，是自然语言处理的最佳工具。

## 语法要素

正则表达式默认所有字符与自己匹配，通过约定一组语法要素来表达人类语言难以精准描述的字符串模式，从而达到更加灵活与精确识别自然语言的目的。

正则表达式的基本约定如下，

|符号|含义|
|-----|-------------|
|`.`|代表任意字符|
|`^`、`$`|开始与结束|
|`*`|重复任意次|
|`+`|至少重复一次|
|`?`|0或1次|
|`{m,n}`|重复m至n（包含）次|
|`{m,}`|至少重复m次|
|`{m}`|重复m次|
|`()`|字符组合|
|`|`|或|
|`[]`|字符集合|
|`[0-9]`|数字字符集|
|`[a-zA-Z]`|英文字符集|
|`\<`、`\>`|单词开始或结束位置的空白符|
|`\b`|单词两边的空白字符|
|`\B`|非单词两边的空白字符|

除此之外，还约定了一组有特殊含义的字符集合，这些字符集合在使用时需要再嵌套一组`[]`。

|符号|含义|
|-----|-------------|
|`[:alpha:]`|字母|
|`[:digit:]`|数字|
|`[:alnum:]`|字母或数字；`\w`与`[[:alnum:]]`同义，`\W` 与`[^[:alnum:]]`同义|
|`[:graph:]`|可见字符，不包括空白|
|`[:lower:]`|小写字母|
|`[:upper:]`|大写字母|
|`[:print:]`|可见的字符和空白|
|`[:punct:]`|标点|
|`[:space:]`|空白符，包括`\t`,`\r`,`\n`；`\s`与`[[:space:]]`同义，`\S`与`[^[:space:]]` 同义|
|`[:xdigit:]`|十六进制数|
|`[\u4e00-\u9fa5]`|中文字符|

由于上述特殊字符被占用，需要转义操作来表达特殊字符自身，有三种约定：基础正则表达式、扩展正则表达式与`Perl`正则表达式。在基础正则表达式中，特殊字符（`?+*{[`等）是字符本身，需要特殊含义得加上`\`来表达其正则表达式含义（例如`\?`表示重复0次或1次，而`?`表示问号本身）。扩展正则表达式相反，用特殊字符默认表达正则含义，而加上`\`后表示字符本身。Perl正则表达式则把扩展正则表达式扩展到更大的范围，与`Perl5`语言正则表达式有同样功能。

## grep命令

`grep`命令的基本功能是，检验输入的第一行是否与正则表达式匹配，若是则输出该行。`grep`命令使用基本正则表达式，`grep -E`可以指定使用扩展正则表达式。由于，该命令使用频率很高，因此直接被封装为`egrep`命令。`-n`参数可以输出匹配结果所在行数，`-v`参数表示返回不包括后续正则表达式的行。


```bash
seq 10000 | egrep -n '^23{2,4}$'
```

```
## 233:233
## 2333:2333
```
在实践中，`egrep`经常会配合其他命令使用，例如找出当前进程中的python进程。

```bash
seq 10000 | egrep -n '^23{2,4}$'
```

```
## 233:233
## 2333:2333
```

## sed命令
是 stream editor，在“流”上进行编辑。`sed`常用的操作是替换，可以使用正则表达式

-r 扩展正则表达式

## awk命令

## R语言字符串处理函数

教学案例做好

## Python的re模块

去除所有中文字符间的空格例子，在这个案例中，我们要得到什么呢？来处理处理。