# Objects
-------------

## Equity


The Equity Object is the primary object necessitated for operation of the library. It contains the timeseries (OHLC) data alongside the ticker, overview information,
financials and others. Through this object it is possible to construct

**How to Initialise?**

    equity = eqkit.Equity(ticker='AAPL', datafeed=eqkit.feeds.YFinance())


### Supported Data Types
------------------------

#### Timeseries Data


#### `Overview()`

This method downloads the overview data from the specified `datafeed`, it returns the DataFrame and also 
saves it onto the object.

    equity.Overview()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `IncomeStatement()`

    equity.IncomeStatement()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `BalanceSheet()`


    equity.BalanceSheet()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `CashFlow()`


    equity.CashFlow()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `Ratings()`

    equity.Ratings()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `Holders()`

    equity.Holders()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `Float()` 

    equity.Float()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `News()`

    equity.News()

**Requires:** None

**Returns:** obj: pandas.DataFrame

#### `MutualFunds()`

    equity.MutualFunds()

**Requires:** None

**Returns:** obj: pandas.DataFrame

### Quantitative Summary
-------------------------

    equity.quant_summary(rfr=0)

**Requires:** None

**Returns:** obj: pandas.DataFrame

### Valuation
--------------

    equity.value(valuation=eqkit.Model, **kwargs)

**Requires:** None

**Returns:** float: priceTarget

#### Study
------------

    equity.Study(study=eqkit.Study, **kwargs)

**Requires:** None

**Returns:** None -- plots instead

### Plotting Timeseries
---------------------------
We can easily plot the prices of an equity using the `.plot()` method. Using matplotlib,
we can see a visualization of the OHLC dataset. 

* **Mode (str):** "N": nominal & "L": logarithmic
* **Period (int):** specifies number of days (back) to plot
* **Indicators (arr):** An array of EQKit.ta.indicator objects


    equity.plot(mode, indicators, period)

**Requires:** str: mode, arr: indicators, int: period

**Returns:** obj: pandas.DataFrame


    equity.plot(mode='N', indicators=[EQKit.ta.indicators.VWAP(14)], 252)

The above Statement returns the normal price plot over the last year (252 days) and superimposes a 14-day VWAP.

### Plotting Other Data
---------------------------

#### `plot_balancesheet(str: parameter)`


#### `plot_incomestatement(str: parameter)`


#### `plot_cashflow(str: parameter)`


#### `plot_holders(str: parameter)`


### Save-State
---------------

#### `save(str: path)`


#### `load(str: path)`


### Architecture
-----------------