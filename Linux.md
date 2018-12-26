SyntaxEditor Code Snippet

# Note 
## Linux 
### Summary in work  

1. Run multiple commands in one single command in backend:
just use & instead of ;

Example:
>cd KPI/ && nohup spark-submit --queue dev daily_KPI.py & cd KPI/ && nohup spark-submit --queue dev daily_late.py & cd KPI/ && nohup spark-submit --queue dev pickup.py &

