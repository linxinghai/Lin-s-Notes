# Pandas
#runoob 

## 安装

>[!code]
>pip install pandas

使用库
import pandas

## Series

```python
import pandas as pd  
  
a = [1, 2, 3]  
  
myvar = pd.Series(a)  
  
print(myvar)
```

## DataFrame

```python
import pandas as pd  
  
data = [['Google',10],['Runoob',12],['Wiki',13]]  
  
df = pd.DataFrame(data,columns=['Site','Age'],dtype=float)  
  
print(df)
```

## CSV

```python
import pandas as pd
df = pd.read_csv('test.csv')
print(df.to_string())
```

```python
import pandas as pd  
     
# 三个字段 name, site, age  
nme = ["Google", "Runoob", "Taobao", "Wiki"]  
st = ["www.google.com", "www.runoob.com", "www.taobao.com", "www.wikipedia.org"]  
ag = [90, 40, 80, 98]  
     
# 字典  
dict = {'name': nme, 'site': st, 'age': ag}  
       
df = pd.DataFrame(dict)  
   
# 保存 dataframe  
df.to_csv('site.csv')
```

## JSON
```JSON
[ 
	{ 
	"id": "A001", 
	"name": "菜鸟教程", 
	"url": "www.runoob.com", 
	"likes": 61 
	}, 
	{ 
	"id": "A002", 
	"name": "Google", 
	"url": "www.google.com", 
	"likes": 124 
	}, 
	{ 
	"id": "A003", 
	"name": "淘宝", 
	"url": "www.taobao.com", 
	"likes": 45 
	} 
]
```

```python
import pandas as pd  
  
df = pd.read_json('sites.json')  
     
print(df.to_string())
```

## 数据清洗

```python
import pandas as pd  
  
df = pd.read_csv('property-data.csv')  
  
print (df['NUM_BEDROOMS'])  
print (df['NUM_BEDROOMS'].isnull())
```
