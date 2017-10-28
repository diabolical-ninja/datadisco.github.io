# Handy Tricks for Python

## Common Libraries

Some handy, common libraries

```python
pip install tqdm
pip install pyodbc
pip install plotly
pip install h2o
pip install distance
pip install slackClient
pip install dash==0.17.7  
pip install dash-renderer==0.7.4
pip install dash-html-components==0.7.0
pip install dash-core-components==0.12.0
pip install plotly==2.0.13
```


## Column Wise Binariser

The pandas function `get_dummies` is great but can cause memory issues with datasets that have many categories or lots of data. This function applies it column by column, which while much slower requires much less memory.

```python
import pandas as pd

def column_binariser(df, columns):
    catlist = []

    for i in columns:
        catlist.append(pd.get_dummies(data=df[i], prefix=str(i)))

    dfbin = pd.concat(catlist, axis=1)
    dfrem = df.drop(columns, axis=1)
    dfcon = pd.concat([dfbin, dfrem], axis=1)        
    
    return dfcon
```
	
	
	
## ODBC Connection & Query

```python
import pandas as pd

cnxn = pyodbc.connect("DRIVER={SQL SERVER};SERVER=<server name>")
df = pd.read_sql(con = cnxn, sql = "<SQL Query>")
```