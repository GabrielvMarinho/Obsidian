A guide of [[Data Science]] to use [[MatPlotLib]] and [[Yfinance]] in [[Python]]


## Importing the [[Lib]]s

```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import pandas_datareader.data as web

!pip install yfinance===0.2.18 --upgrade --no-cache-dir

import yfinance as yf
yf.pdr_override()
```

## Getting a dataframe

```
ibov = web.get_data_yahoo("^BVSP")
```

## Setting a chart

```
ibov["Close"].plot(figsize=(20, 10), label="IBOV")

ibov["Close"].rolling(200).mean().plot(label="M200")
plt.legend()
```


## Using [[Seaborn]] to style better

```
sns.set()
```

this will instantly style the charts already done at some point without having to actually style it

## Correlation

```
sns.heatmap(carteira.corr(), annot=True)
```