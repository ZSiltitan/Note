# Note 
## SQL 
### Improve SQL searching efficiency  
1. Use more where and limit to avoid scan the whole table
2. Use key with index in the condition
3. Where clause:
-  Avoid using != or <> in where clause
- Avoid judging null in where clause
4. (If can), use b

5. 
After adding

>TIMETAB AS
(
	SELECT date_add(current_date,-1) as currentdate,
	'a' as index
)

>FROM TIMETAB
LEFT JOIN SLATB
ON TIMETAB.index = SLATB.index
LEFT JOIN SLATBSAMEDAY 
ON TIMETAB.index = SLATBSAMEDAY.index 
LEFT JOIN DPTB
ON TIMETAB.index = DPTB.index
LEFT JOIN DPTBNotDel
ON TIMETAB.index = DPTBNotDel.index
LEFT JOIN WHDCTB 
ON TIMETAB.index = WHDCTB.index
LEFT JOIN 
WHDCTB2 
ON TIMETAB.index = WHDCTB2.index
LEFT JOIN 
DURATAB 
ON TIMETAB.index = DURATAB.index

Report Error: Detected implicit cartesian product for LEFT OUTER join between logical plans

It's join's problem (maybe has duplicates)