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