An example of how to do a program to select random wallets and compare it to the [[IBOV]] index with [[Python]]

We will use these [[Lib]]s:
1. [[Yfinance]]
2. [[Random (Python)]]
3. [[MatPlotLib]]
4. [[Pandas]]
5. [[Numpy]]

We are going to get all the [Brazil](obsidian://open?vault=Obsidian&file=Countries%2FBrazil%2FBrazil) [[Stock]]s and compare to index that should reflect said performance
The code:
```
//getting all the stocks
tickers_ibov = "ABEV3.SA AZUL4.SA B3SA3.SA BBAS3.SA BBDC3.SA BBDC4.SA BBSE3.SA BPAC11.SA BRAP4.SA BRFS3.SA BRKM5.SA CASH3.SA CCRO3.SA CIEL3.SA CMIG4.SA COGN3.SA CPFE3.SA CRFB3.SA CSAN3.SA CSNA3.SA CVCB3.SA CYRE3.SA DXCO3.SA ELET3.SA ELET6.SA EMBR3.SA ENBR3.SA EQTL3.SA GGBR4.SA GOAU4.SA HAPV3.SA HYPE3.SA ITSA4.SA ITUB4.SA JHSF3.SA KLBN11.SA LREN3.SA MGLU3.SA MRFG3.SA MRVE3.SA MULT3.SA NTCO3.SA PETR3.SA PETR4.SA POSI3.SA PRIO3.SA QUAL3.SA RADL3.SA RAIZ4.SA RDOR3.SA RECV3.SA SANB11.SA SBSP3.SA SULA11.SA SUZB3.SA TAEE11.SA TIMS3.SA TOTS3.SA UGPA3.SA USIM5.SA VALE3.SA VIIA3.SA VBBR3.SA WEGE3.SA YDUQ3.SA"

  

dados_yahoo = yf.download(tickers=tickers_ibov, period="1y")["Adj Close"]

  

ibov = yf.download("BOVA11.SA", period="1y")["Adj Close"]

ibov = ibov / ibov.iloc[0]

//cleaning the dataset
dados_yahoo.dropna(how='all', inplace=True)
dados_yahoo.dropna(axis=1, inplace=True, thresh=246)

//working with percentages
retorno = dados_yahoo.pct_change()
retorno_acumulado = (1+retorno).cumprod()

retorno_acumulado.iloc[0] = 1

carteira = random.choices(dados_yahoo.columns, k=5)
carteira = 10000 * retorno_acumulado.loc[: , carteira]
carteira['saldo'] = carteira.sum(axis=1)
carteira["retorno"] = carteira["saldo"].pct_change()

//setting all the random wallets in the same chart as the ibov
for i in range(1000):
  carteira = random.choices(dados_yahoo.columns, k=5)
  carteira = 10000 * retorno_acumulado.loc[: , carteira]
  carteira['saldo'] = carteira.sum(axis=1)
  carteira["saldo"].plot(figsize=(18, 12))

  
(ibov*50000).plot(linewidth=4, color="black")

//You should put more wallets to get close to the actual chance 

```