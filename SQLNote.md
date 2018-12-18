# Note 
## SQL 
### Improve SQL searching efficiency  
1. Use more where and limit to avoid scan the whole table
2. Use key with index in the condition
3. Where clause:
-  Avoid using != or <> in where clause
- Avoid judging null in where clause
4. (If can), use b