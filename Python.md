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
2. 