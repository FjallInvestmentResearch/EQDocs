# Data Feeds
---------------

Feeds are the main connectivity providers for EQKit, they enable the system to identify and retrieve the correct data upon request.
With modularity in mind, feeds were designed such that they can be easily modified, expanded or changed all-together; the key part being the
default feed (see below).
Feeds are necessary to download data using EQKit.

## YFinance
--------------
This data feed provides connectivity to the [Yahoo Finance API](https://policies.yahoo.com/us/en/yahoo/terms/product-atos/apiforydn/index.htm)
via the [yfinance python library](https://github.com/ranaroussi/yfinance) developed by Ran Aroussi. It is unique as it does not
require an API_KEY and also has no request limit. This is recommended as the default datafeed for Equity & ETF dsta for personal use. 

* [Documentation](https://github.com/ranaroussi/yfinance)
* **Supported Version:** 0.1.74
* **Needs API Key?** No

### Reference
---------------

    Feed = eqkit.feeds.YFinance()


#### `get_info(str: symbol)`

Downloads overview information for an `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_info('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_ETF_info(str: symbol)`

Downloads overview information for an `ETF()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_ETF_info('SPY')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_price(str: symbol)`

Downloads and returns the current price as a float.

    from eqkit.feeds import YFinance as feed

    feed().get_price('AAPL')

**Requires:** str: symbol

**Returns:** float: price

#### `get_DailyKlines(str: symbol)`

Downloads :abbr:`OHLC (Open-High-Low-Close)` data for the specified symbol.

    from eqkit.feeds import YFinance as feed

    feed().get_DailyKlines('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_BalanceSheet(str: symbol)`

Downloads the Annual Balance Sheet of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_BalanceSheet('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_incomeStatement(str: symbol)`

Downloads the Annual Income Statement of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_incomeStatement('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_cashFlow(str: symbol)`

Downloads the Annual Cash Flow Statement of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_cashFlow('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_Fund_Sectors(str: symbol)`

Downloads the Sector Weights of a specified ticker and is only available through the `ETF()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_Fund_Sectors('SPY')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_Fund_Holdings(str: symbol)`

Downloads the Top Holdings of a specified ticker and is only available through the `ETF()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_Fund_Holdings('SPY')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_ratings(str: symbol)`

Downloads the Analyst Ratings of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_ratings('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_priceTargets(str: symbol)`

Downloads the Analyst Price Targets of a specified ticker and is only available through the `Equity()` object.

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

    from eqkit.feeds import YFinance as feed

    feed().get_priceTargets('AAPL')

#### `get_news(str: symbol)`

Downloads the News feed of a specified ticker.

    from eqkit.feeds import YFinance as feed

    feed().get_news('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_holders(str: symbol)`

Downloads the Top Holders of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_holders('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame


#### `get_float(str: symbol)`

Downloads the Float Composition of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_float('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_mutualholders(str: symbol)`

Downloads the Top Mutual Fund Holders of a specified ticker and is only available through the `Equity()` object.

    from eqkit.feeds import YFinance as feed

    feed().get_mutualholders('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame


## AlphaVantage
---------------

The [AlphaVantage API](https://www.alphavantage.co/) provides access to quality global equity data through both a free and paid API. Users get a 500 call-a-day limit and can download a 
plethora financial data, such as OCHL, fundamentals and, macroeconomic timeseries. The API data feed is connected using the `requests` library and is 
built in-house. 

* [Documentation](https://www.alphavantage.co/documentation/)
* **Supported Version:** N/A
* **Needs API Key?** Yes [FREE](https://www.alphavantage.co/support/#api-key)

-


    Feed = eqkit.feeds.AlphaVantage('YOUR-API-KEY-HERE')


### Supported Macro Data
---------------------------

When generating Macro `Timeseries` using AlphaVantage, users need to input a valid data id from the following list.

* GDP: Gross Domestic Product
* GDP_PC: Gross Domestic Product, Per Capita
* FUNDS_RATE: Federal Funds Rate 
* CPI: Consumer Price Index
* INFLATION: Inflation Rate
* INFLATION_EXPECTATION: Inflation Expectation
* SENTIMENT: Consumer Sentiment
* RETAIL: Retail Sales
* DURABLES: Durable Good Orders
* UNEMPLOYMENT: Unemployment Rate
* NONFARM: Non-farm payroll 

### Reference
----------------

#### `get_info(str: symbol)`

Downloads overview information for an `Equity()` object.

    Feed.get_info('AAPL')

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_price(str: symbol)`

Returns latest price as float.

    Feed.get_price('AAPL')

**Requires:** str: symbol

**Returns:** float: price

#### `get_DailyKlines(str: symbol)`

Returns a pandas DataFrame with sorted, timestamped OHLC data on the specified ticker. As mentioned, this library only supports a daily timeframe.

    Feed.get_DailyKlines('AAPL')

**Requires:** str: symbol

**Returns:** obj: pd.DataFrame

#### `get_BalanceSheet(str: symbol)`

Returns a pandas DataFrame of the Annual Balance Sheet, as supported by the `Equity()` object. This requires an AlphaVantage Premium API Account.

    Feed.get_BalanceSheet('AAPL')

**Requires:** str: symbol

**Returns:** obj: pd.DataFrame

#### `get_incomeStatement(str: symbol)`

Returns a pandas DataFrame of the Annual Income Statement, as supported by the `Equity()` object. This requires an AlphaVantage Premium API Account.  

    Feed.get_incomeStatement('AAPL')

**Requires:** str: symbol

**Returns:** obj: pd.DataFrame

#### `get_news(str: symbol)`

Returns a pandas DataFrame of the latest news for the selected ticker. This endpoint includes a sentiment reading on each story.

    Feed.get_news('AAPL')

**Requires:** str: symbol

**Returns:** obj: pd.DataFrame

#### `get_macro_series(str: id)`

Returns a pandas DataFrame of the macroeconomic data available (as detailed in the above section) by the provider. 

    Feed.get_macro_series('RETAIL')

**Requires:** str: symbol

**Returns:** obj: pd.DataFrame

#### `check_limit()`


#### `valid_macro()`


## Federal Reserve (FRED)
---------------------------

This data feed uses `requests` to wrap the Federal Reserve of St. Louis (FRED) API which can be used to retrieve an array of macroeconomic timeseries. 
The only operation supported by the package is a query for data which can be made by using the relevant timeseries id, as reported on the FRED database. 


* [Documentation](https://fred.stlouisfed.org/docs/api/fred/)
* **Supported Version:** N/A
* **Needs API Key?** Yes [FREE](https://fred.stlouisfed.org/docs/api/api_key.html)

a

    feed = eqkit.feeds.FredAPI("YOUR-API-KEY-HERE")



### Reference
---------------

#### `get_macro_series(str: id, str: start)`

Returns a pandas Series object containing the timeseries values for the specified data timeseries from the FRED API database, this is passed using the *id* parameter. The Start
date of the timeseries is passed in string format via the *start* parameter.

    feed.get_macro_series(id='CAPISCOL', start='01-01-2010')

**Requires:** str: id, str: start
**Returns:** pd.Series


## Binance
-----------

This datafeed API is a wrapper for the [python-binance](https://python-binance.readthedocs.io/en/latest/) package developed by Sam McHardy which can be used to connect to the
cryptocurrency exchange to retrieve Spot & Derivatives data. This implementation of the wrapper is derived from Crypto CSuite product however, has limited functionality and currently
only supports spot timeseries data for crypto price studies. It requires an active Binance account and associated SHA keys to connect. 

* [Documentation](https://python-binance.readthedocs.io/en/latest/)
* **Supported Version:** v1.0.16
* **Needs API Key?** Yes [FREE with Binance Account](https://www.binance.com/en/support/faq/how-to-create-api-360002502072)


### Reference
--------------
Below is a comprehensive list of all the methods currently included in the API wrapper. 

#### `__init__(str: API_KEY, str: SECRET_KEY)`

Initialises the Binance API client.

    feed = EQKit.feeds.Binance(API_KEY='MY_KEY', SECRET_KEY='MY_SECRET_KEY')

**Requires:** str: API_KEY, str: SECRET_KEY

**Returns:** EQKit.Datafeed

#### `get_DailyKlines(str: symbol)`

Returns the OHLCV pandas DataFrame with the specified symbol data.  

    feed.get_DailyKlines(symbol='BTCUSDT')

**Requires:** str: symbol

**Returns:** pd.DataFrame

#### `get_crypto_info(str: symbol)`

Returns a 1 row pandas DataFrame object with summary information about the selected cryptocurrency pair.

    feed.get_crypto_info(symbol='BTCUSDT')

**Requires:** str: symbol

**Returns:** pd.DataFrame

#### `get_price(str: symbol)`

Returns a float of the last 5 minutes VWAP as the latest price; useful for scanner functions.


    feed.get_price(symbol='BTCUSDT')

**Requires:** str: symbol

**Returns:** float


## Capital.gr
------------------

This is a custom resting requests based wrapper API for the Capital.gr website that streams delayed data from the Athens Exchange (ATHEX). This
module has been designed to retrieve Index data which is not published elsewhere. It does not need an API key to operate. 
It currently includes 21 indices.

### Reference
---------------

Below is a comprehensive list of all the methods included in the API.

#### `list()`

Returns a formated printed list of the available indices.

    feed.list()

**Requires:** None

**Returns:** print

#### `get_index(str: ticker, bool: smoothing)`

Returns a pandas Timeseries data object with the closing issue of the selected index. The *smoothing* bool setting specifies whether the data should be smoothed for outliers.

    feed.get_index(ticker='FTSE', smoothing=True)

**Requires:** str: ticker, bool: smoothing

**Returns:** pd.Series

#### `get_timeSeries(str: symbol, bool: smoothing)`

Returns a Timeseries object with the closing price of the selected index. The *smoothing* bool setting specifies whether the data should be smoothed for outliers.

    feed.get_timeSeries(ticker='FTSE', smoothing=True)

**Requires:** str: ticker, bool: smoothing

**Returns:** EQKit.Timeseries

#### `search(str: query, bool: lucky)`

Returns a proximity match top-5 data-frame for the selected query. If lucky is specified then the return object is a ready-made timeseries.

    feed.search(query='General', lucky=False)

**Requires:** str: query, bool: lucky

**Returns:** pd.DataFrame or EQKit.Timeseries

#### `catalogue()`

Returns the available index data list in computer-readable format, `dict`.

    feed.catalogue()

**Requires:** None

**Returns:** dict

## Google Trends
-------------------

### Reference
--------------------

## IEX Cloud
-------------

## Default Feed
-----------------

### Reference
---------------
    
#### `init()`

Initialises the default feed.

**Requires:** None

**Returns:** None


#### `set_id(str: id)`

Sets the exchange id. Used in internal methods.

**Requires:** str: id

**Returns:** self

#### `get_timeSeries(str: symbol)`

Returns a `timeseries` object with symbol and filled data, ready to be packaged in `Equity` or `ETF`.

**Requires:** str: symbol

**Returns:** obj: timeseries

#### `get_Overview(str: symbol)`

Returns a pandas DataFrame containing the relevant Overview information for the `Equity` as specified in `get_info()`

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_ETFOverview(str: symbol)`

Returns a pandas DataFrame containing the relevant Overview information for the `ETF` as specified in `get_ETF_info()`

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_Macro(str: id, str: axis)`

Returns a `timeseries` object with macroeconomic data, used to parse non-asset data inputs (see, FRED).
It requires the data identifier `id` and the axis on which the data lie (if not 'price').

**Requires:** str: id, str: axis

**Returns:** obj: timeseries

#### `get_price(str: symbol)`

Returns a `float` price for the symbol selected.

**Requires:** str: symbol

**Returns:** float: price

#### `get_priceTargets(str: symbol)`

Returns a Data Frame with the estimated analyst target prices; this is designed as a wrapper for functionality found in
yfinance library.

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_ratings(str: symbol)`

Returns a Data Frame with the analyst ratings; this is designed as a wrapper for functionality found in
yfinance library.

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_news(str: symbol)`

Returns a Data Frame with the latest timestamped news.

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame

#### `get_holders(str: symbol)`

Returns a Data Frame with the largest institutional holders; this is designed as a wrapper for functionality found in
yfinance library.

**Requires:** str: symbol

**Returns:** obj: pandas.DataFrame