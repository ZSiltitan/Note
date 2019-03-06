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


6. 在linux下，不可避免的会用VIM打开一些windows下编辑过的文本文件。我们会发现文件的每行结尾都会有一个^M符号，这是因为 DOS下的编辑器和Linux编辑器对文件行末的回车符处理不一致， 
对于回车符的定义： 
windows：0D0A 
unix\linux: 0A 
MAC: 0D 
比较快捷的去除这些符号的方法有这么几种： 
（1）是用VI的命令： 
    使用vi打开文本文件 
    vi dos.txt 
    命令模式下输入 
    :set fileformat=unix 
    :w 
(2) VI下使用正则表达式替换 
   g/\^M/s/\^M// 
    或者 
   %s/^M//g 
（3）使用sed 工具 
    sed ’s/^M//’ filename > tmp_filename 
（4）既然window下的回车符多了‘\r’，那么当然通过删除‘\r’ ，也可以实现： 
    tr -d '\r' 
（5）最后一个方法是本人最常用的方法，个人觉得最方便 
    在终端下敲命令： 
    $ dos2unix filename 
    直接转换成unix格式，就OK了！～  
	

7. Mission fail and restart

#!/bin/bash
module_name="hive_to_hdfs"
function run_workflow {
    echo $(date +%FT%T)" [${module_name}] - Start"
    status="fail"
    local wait_duration=60
    local max_wait=60
    local attempt=0
    while [[ ${status} == "fail" && ${attempt} < 1 ]]; do
        echo $(date +%FT%T)" [${module_name}] - Starting Attempt #"${attempt}
        echo $(date +%FT%T)" [${module_name}] - args: $@"


        main $@

        if [ $? -ne 0 ]; then
            exit 1
        else
            status="success"
        fi
    done
    if [ ${status} == "fail" ]; then
        echo $(date +%FT%T)" [${module_name}] - Failed"
        exit 1
    fi
}

run_workflow $@
