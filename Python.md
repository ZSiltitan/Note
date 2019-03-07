
SyntaxEditor Code Snippet

# Python 
### Pandas     
1. Insert Rows
```
```
2. pd.ExcelWriter(file,engine = 'xlsxwriter')
```
>>>writer = pd.ExcelWriter(FiletoWrite,engine = 'xlsxwriter')
>>>data = pd.read_excel('sample.xlsx')
>>>data.to_excel(writer, sheet_name = 'sheet1', index = False/True)
```
*Until here, if there already a  'writer' excel file, then the to_excel will write sheet into the excel document.*
**Notice: If not have the 'writer' file, then the excel document will not be created.
Until**
```
>>>writer.save()
```
Then the excel is created with the imported sheets.

3. read_csv('xxx.csv', **index_column** = 0)

Could get rid of the 'Unnamed: 0' when read csv     

4. to_csv('xxx.csv', **index = False**)
Generate csv file without the index column 'Unnamed: 0'

### gspread     
1. import_csv(sheet.id, data)
```
data = open('data.csv').read()
# Get sheet_id from the link of your google sheet # https://docs.google.com/spreadsheets/d/1H5orsHF1k8IVqWDxAHv6xQwZlxIwlXpBJOvDgBUBeL0/edit#gid=1808900108 # String between 'd/' and '/edit' is your sheet.id  gc.import_csv('1H5orsHF1k8IVqWDxAHv6xQwZlxIwlXpBJOvDgBUBeL0',wk)
```
### datetime  
1. datetime.datetime.strptime(date,'%Y-%m-%d')
Turn string into datetime.datetime
*%Y-%m-%d   %H:%M:%S*
```
>>> holiday = datetime.datetime.strptime('2018-01-01','%Y-%m-%d')
>>> holiday
datetime.datetime(2018, 8, 31, 0, 0)
```
2. datetime.datetime.strftime('%Y-%m-%d')
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
4. locals()    
```
>>>for i in range(7,13,1):
	   locals()['df2017_'+str(i)] = pd.read_csv('2017combine' + str(i) +'.csv')
	   print ('2017combine' + str(i) +'.csv')
2017combine7.csv
2017combine8.csv
2017combine9.csv
2017combine10.csv
2017combine11.csv
2017combine12.csv
```
动态生成变量
5. eval()    
执行字符串表达式
```
def add_column(df,month):
    df['Month']=month
for i in range(7,13,1):
    add_column(eval('df2017_'+str(i)),i)    
```
using eval() can call the **df2017_x** variable and achieve the add_column function
使用eval()功能可以执行字符串中的表达式，可以动态调用变量

6. reset_index

reset_index的作用是重新设置dataframe的index，范围为0~len(df)    

    result= pd.DataFrame(np.arange(9).reshape((3, 3)), index=['1', '5', '6'], columns=['c1', 'c2', 'c3'])
    result2= result.reset_index()

会生成新的一列，列名“index”，用来保存原来的index，并将索引Index变为range(0.len(result))

    result2 = result.reset_index(drop=True)
则会删除原来的Index，直接替换为range(0.len(result))

**reindex**

reindex的作用是按照原有的列进行重新生成一个新的df。

result3 = result.reindex(index=['1','2','3'])

原index并没有发生改变，而因为'2'和'3'是不存在的，所以使用了Nan填充，这个值的内容可以自己填充，可以改为默认填充0或者任意你想要的数据。

### Excel

由于设计目的不同，每个模块通常着重于某一方面功能，各有所长。

1. xlwings

可结合 VBA 实现对 Excel 编程，强大的数据输入分析能力，同时拥有丰富的接口，结合 pandas/numpy/matplotlib 轻松应对 Excel 数据处理工作。

2. openpyxl

简单易用，功能广泛，单元格格式/图片/表格/公式/筛选/批注/文件保护等等功能应有尽有，图表功能是其一大亮点，缺点是对 VBA 支持的不够好。

3. pandas

数据处理是 pandas 的立身之本，Excel 作为 pandas 输入/输出数据的容器。

4. win32com

从命名上就可以看出，这是一个处理 windows 应用的扩展，Excel 只是该库能实现的一小部分功能。该库还支持 office 的众多操作。需要注意的是，该库不单独存在，可通过安装 pypiwin32 或者 pywin32 获取。

5. xlsxwriter

拥有丰富的特性，支持图片/表格/图表/筛选/格式/公式等，功能与openpyxl相似，优点是相比 openpyxl 还支持 VBA 文件导入，迷你图等功能，缺点是不能打开/修改已有文件，意味着使用 xlsxwriter 需要从零开始。

6. DataNitro

作为插件内嵌到 Excel 中，可完全替代 VBA，在 Excel 中使用 python 脚本。既然被称为 Excel 中的 python，协同其他 python 库亦是小事一桩。然而，这是付费插件...

7. xlutils

基于 xlrd/xlwt，老牌 python 包，算是该领域的先驱，功能特点中规中矩，比较大的缺点是仅支持 xls 文件。