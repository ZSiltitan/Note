SyntaxEditor Code Snippet

# Note 
## Linux 
### Summary in work  

1. Run multiple commands in one single command in backend:
just use & instead of ;

Example:
>cd KPI/ && nohup spark-submit --queue dev daily_KPI.py & cd KPI/ && nohup spark-submit --queue dev daily_late.py & cd KPI/ && nohup spark-submit --queue dev pickup.py &

2. 命名shell变量时，中间不能有空格，可以使用下划线（_）。
3. 使用vim命令时 后面必须添加文件名
4. 完整的表达式要被 ` ` 包含，注意这个字符不是常用的单引号，在 Esc 键下边。
5. 原生bash不支持简单的数学运算，但是可以通过其他命令来实现，例如 awk 和 expr，expr 最常用。

expr 是一款表达式计算工具，使用它能完成表达式的求值操作。
完整的表达式要被 ` ` 包含，注意这个字符不是常用的单引号，在 Esc 键下边。

>#!/bin/bash 
>val=`expr 2 + 2` 
>echo "两数之和为 : $val"
>>两数之和为  :  4

两点注意：

表达式和运算符之间要有空格，例如 2+2 是不对的，必须写成 2 + 2，这与我们熟悉的大多数编程语言不一样。
完整的表达式要被 ` ` 包含，注意这个字符不是常用的单引号，在 Esc 键下边。

    echo `expr 1+4`
	>1+4
	
	echo `expr 1 + 4`
	>5

```
a=10
b=20

val=`expr $a + $b`
echo "a + b : $val"
```

乘号(*)前边必须加反斜杠(\)才能实现乘法运算；
```
val=`expr $a \* $b`
echo "a * b : $val"
```


6. 