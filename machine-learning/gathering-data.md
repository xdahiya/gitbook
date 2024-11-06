---
description: how many ways we can gather required data
---

# Gathering Data

## <mark style="background-color:blue;">CSV</mark>

## Opening a local csv file <a href="#id-2.-opening-a-local-csv-file" id="id-2.-opening-a-local-csv-file"></a>

`df = pd.read_csv('aug_train.csv')`



## Opening a csv file from an URL <a href="#id-3.-opening-a-csv-file-from-an-url" id="id-3.-opening-a-csv-file-from-an-url"></a>

`import requests from io import StringIO`

`url = "https://raw.githubusercontent.com/cs109/2014_data/master/countries.csv" headers = {"User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:66.0) Gecko/20100101 Firefox/66.0"} req = requests.get(url, headers=headers) data = StringIO(req.text)`

`pd.read_csv(data)`



## Sep Parameter <a href="#id-4.-sep-parameter" id="id-4.-sep-parameter"></a>

`pd.read_csv('movie_titles_metadata.tsv',sep='\t',names=['sno','name','release_year','rating','votes','genres'])`



## Index\_col parameter <a href="#id-5.-index_col-parameter" id="id-5.-index_col-parameter"></a>

`pd.read_csv('aug_train.csv',index_col='enrollee_id')`



## Header parameter <a href="#id-6.-header-parameter" id="id-6.-header-parameter"></a>

`pd.read_csv('test.csv',header=1)`



## use\_cols parameter <a href="#id-7.-use_cols-parameter" id="id-7.-use_cols-parameter"></a>

`pd.read_csv('aug_train.csv',usecols=['enrollee_id','gender','education_level'])`



## Squeeze parameters <a href="#id-8.-squeeze-parameters" id="id-8.-squeeze-parameters"></a>

`pd.read_csv('aug_train.csv',usecols=['gender'],squeeze=True)`&#x20;

`sequence`



## Skiprows/nrows Parameter <a href="#id-9.-skiprows-nrows-parameter" id="id-9.-skiprows-nrows-parameter"></a>

`pd.read_csv('aug_train.csv',nrows=100)`



## Encoding parameter <a href="#id-10.-encoding-parameter" id="id-10.-encoding-parameter"></a>

`pd.read_csv('zomato.csv',encoding='latin-1')`



## Skip bad lines <a href="#id-11.-skip-bad-lines" id="id-11.-skip-bad-lines"></a>

`pd.read_csv('BX-Books.csv', sep=';', encoding="latin-1",error_bad_lines=False)`



## dtypes parameter <a href="#id-12.-dtypes-parameter" id="id-12.-dtypes-parameter"></a>

`pd.read_csv('aug_train.csv',dtype={'target':int}).info()`



## Handling Dates <a href="#id-13.-handling-dates" id="id-13.-handling-dates"></a>

`pd.read_csv('IPL Matches 2008-2020.csv',parse_dates=['date']).info()`



## Convertors <a href="#id-14.-convertors" id="id-14.-convertors"></a>

`pd.read_csv('IPL Matches 2008-2020.csv',converters={'team1':rename})`



## na\_values parameter <a href="#id-15.-na_values-parameter" id="id-15.-na_values-parameter"></a>

`pd.read_csv('aug_train.csv',na_values=['Male',])`



## Loading a huge dataset in chunks <a href="#id-16.-loading-a-huge-dataset-in-chunks" id="id-16.-loading-a-huge-dataset-in-chunks"></a>

`dfs = pd.read_csv('aug_train.csv',chunksize=5000)`

##

## <mark style="background-color:blue;">JSON Format</mark>

`pd.read_json('train.json')`

`pd.read_json('https://api.exchangerate-api.com/v4/latest/INR')`

## SQL

for working with sql first you need to run sql file in a db to insert all data into database

you can click import



then you need library mysql.connector

```
!pip install mysql.connector
```

create a connection first using connector library&#x20;

then you can read data like this



`import mysql.connector`

`conn = mysql.connector.connect(host='localhost',user='root',password='',database='world')`

`df = pd.read_sql_query("SELECT * FROM countrylanguage",conn)`



## Fetching From Api

`import pandas as pd`&#x20;

`import requests`

`df = pd.DataFrame()`

`for i in range(1,429): response = requests.get('https://api.themoviedb.org/3/movie/top_rated?api_key=8265bd1679663a7ea12ac168da84d2e8&language=en-US&page={}'.format(i)) temp_df = pd.DataFrame(response.json()['results'])[['id','title','overview','release_date','popularity','vote_average','vote_count']] df = df.append(temp_df,ignore_index=True)`



## Web Scraping

you can use puppeteer in nodejs

selenium,requests,bs4 in python

