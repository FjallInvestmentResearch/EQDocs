# Feeds
---------------

## A World of Supported Data

## Feed Connectivity to Objects

In normal operation, a user would not call the data feed directly, but instead use it on an instantiated object like an `Equity`. However, data feeds are a key feature
for users looking to download and aggregate financial data through EQKit. The structure of the relationship between the data feed and object means that the data feed package is easily 
expandable to other providers or to include new features. Although, the most important aspect of the library in this regard is interoperability across data feeds. This is possible as 
the objects are exchange agnostic while the `Scanner` aggregation tool accounts for the set data feed. 

**What API keys do I need?**
You can test most functionality without a key, simply by using the `YFinance()` data feed. However, for full functionality we recommend that users acquire at least a key for the 
`FredAPI()` and `Binance()` data feeds to cover the Macro and Crypto data inputs. 
If you are using another data provider, you can easily build a new data feed to cover your needs!

**Correct Usage**

This example shows proper usage of the `YFinance()` data feed; the requested symbol is that of an equity and the retrival methods are both supported by the feed.

    feed = eqkit.feeds.YFinance()
    stock = eqkit.Equity('AAPL', feed)
    
    stock.Overview()
    stock.News()

**Incorrect Usage**

This first incorrect example showcases code where one is using an `Equity`-only function using a `Crypto` data feed. This action
returns an error.


    feed = eqkit.feeds.Binance("KEY", "OTHER_KEY")
    feed.get_info('AAPL')

This second example presents a scenario which a user is more likely to encounter. Here although the data feed supports equities, we call a method - namely
`Ratings()` which is not supported by the `AlphaVantage` feed. This will also return an error.

    feed = eqkit.feeds.AlphaVantage("KEY")
    equity = eqkit.Equity('AAPL', feed)
    equity.Ratings()

**How does the data feed know what the ticker is?**

*It doesn't!* The data feed is 'raw' and results without proper validation of the retrieved asset data might be problematic and should be kept in mind. 
In normal operation users should not break the data feeds given that only certain data is supported by each major data object.  

## AlphaVantage

## Yahoo Finance

## Binance

### Getting Started
-------------------------

#### Step 1: Activating an API Key

To begin using the Binance API in EQKit one must set up a valid Binance API key-pair for use with external applications. To do this, the user must have an active Binance Account,
not necessarily one with capital or executed trades. You can find a complete guide to doing this [here](https://www.binance.com/en/support/faq/how-to-create-api-360002502072). 
Once that is completed, you will have a string key-pair which you will need to import into the library. 

We will work to include ways of importing encrypted key-pair files.

#### Step 2: Setting up the Client

Once you have the API keys, you can simply use the statement below to connect with the Binance client and then use the feed for crypto data retrival.

    feed = EQKit.feeds.Binance(API_KEY='MY_KEY', SECRET_KEY='MY_SECRET_KEY')

## FRED API

## EUROSTAT

## CBOE

## Google Trends

## NASA Power API

## Capital.gr

### Getting Started
-----------------
The API can be simply initialized by just calling the module. Upon initializing, the API will 'scan' the CapitalGr database and retrieve the updated keys for the included indices.

    feed = EQKit.feeds.CapitalGr()

    index = feed.get_timeSeries(ticker='FTSE', smoothing=True)

The code-block shown above is the simplest way to to get a data object from the API in a usable Timeseries format. This mean it can be easily plotted and used in studies. 


## Greece In Figures

## IEX
