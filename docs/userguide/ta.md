# Technical Analysis

!!! note
    The `ta` module is a core component of the **EQKit** package which is designed around the principles of signal design
    and analysis.


## The Logic of the TA Module
------------------------------
The Technical Analysis (`ta`) module is design around the principles of signal design and analysis while being 
self-contained in its research capabilities and featuring extensive cross-connectivity with other **EQKit** functions.
In this sense the module follows a "bottom-up" approach whereas each indicator (`ta.indicators`) can be used to construct
a signal (`ta.signals`). Finally, these signals can be evaluated using the signal analyser. 

## Technical Indicators 
------------------------------
The technical indicators (`ta.indicators`) are essentially formulas which return numerical values derived from the data
contained in the Timeseries object used (at `Timeseries().data`) for the calculation. Indicators are designed to be light,
functional, and fast; beside from their core function (`apply()`) they can also contain information for the plotting 
look of each indicator (`subplot_formatter()`) when used in the `plot()` method of a core object.

An indicator can be called as follows:
    
    EQKit.ta.indicators.RSI(28).apply(myStock.timeSeries.data)

## Signals
------------------------------

## Signal Analyser
------------------------------

## Plotting Indicators & Signals
----------------------------------


## Building your Own
------------------------------

### Technical Indicators


### Indicator Subplot Formatting


### Signals


### Analyzer Formulas


## Using TA Components Across the Stack
-------------------------------------------

