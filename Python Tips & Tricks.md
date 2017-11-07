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


## Jupyter Slideshow Code Hiding

One of the coolest things about Jupyter is the ability to instantly turn analysis into a presentation. Unfortunately that also comes with all the code used in the analysis, generally not something your audience are interested. This handy snippet removes all code blocks from the resulting presentation.

```javascript
<script>
    var code_show=true; //true -> hide code at first

    function code_toggle() {
        $('div.prompt').hide(); // always hide prompt

        if (code_show){
            $('div.input').hide();
        } else {
            $('div.input').show();
        }
        code_show = !code_show
    }
    $( document ).ready(code_toggle);
</script>
```

To actually generate the deck run the following in your terminal of choice:

```bash
jupyter nbconvert "<notebook name>".ipynb --to slides --post serve
```


## Plotly Time Series

```Python
import plotly.graph_objs as go
import plotly.plotly as py
from plotly import tools
from plotly.offline import download_plotlyjs, init_notebook_mode, plot, iplot

# Allow plotly to operate within the notebook
init_notebook_mode()


# List of df columns to plot
cols = ['col_1','col_2']

data = [go.Scatter(
            x = df['<timestamp col>'],
            y = df[x],
            name = x)
       for x in cols]

layout = go.Layout(
            title = 'My Title',
            xaxis = dict(title = "Timestamp"),
            yaxis = dict(title = "something"
        )
)

fig = go.Figure(data = data, layout = layout)
iplot(fig)
```