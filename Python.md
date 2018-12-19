# Python
## Pandas
1. Insert Rows

## gspread
1. import_csv(sheet.id, data)
```
data = open('data.csv').read()
# Get sheet_id from the link of your google sheet
# https://docs.google.com/spreadsheets/d/1H5orsHF1k8IVqWDxAHv6xQwZlxIwlXpBJOvDgBUBeL0/edit#gid=1808900108
# String between 'd/' and '/edit' is your sheet.id
gc.import_csv('1H5orsHF1k8IVqWDxAHv6xQwZlxIwlXpBJOvDgBUBeL0',wk)
```
## datetime
1. datetime.datetime.strptime(date,'%Y-%m-%d')
Turn string into datetime.datetime
*%Y-%m-%d   %H:%M:%S*
```
>>> holiday = datetime.datetime.strptime('2018-01-01','%Y-%m-%d')
>>> holiday
datetime.datetime(2018, 8, 31, 0, 0)
```
2.  datetime.datetime.strftime('%Y-%m-%d')
```
>>>holiday = datetime.datetime.strptime('2018-01-01','%Y-%m-%d')
>>>holiday.strftime('%Y-%m-%d')
'2018-01-01'
```
3. datetime.timedelta(unit=i)
```
>>>datetime.timedelta(days=1)
datetime.timedelta(1)
```
Use timedelta to modify the datetime.datetime attribute
4. 