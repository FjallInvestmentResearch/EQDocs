# Studies

-----------------

## Main Class

-----------------

### `run()`

### `calc()`

### `plot()`


## Studies Reference

-----------------

### `Autocorrelation`

Autocorrelation(obj: ALPHA, int: lags)

### `CumulativeReturn`

CumulativeReturn(obj: ALPHA, obj: BETA, int: period, bool: vol_match)

### `CalendarPerformance`

CalendarPerformance(obj: ALPHA, str: freq)

### `DynamicCTE`

DynamicCTE(obj: ALPHA, obj: BETA, int: lookback, int: max)

### `Hurst`

Hurst(obj: ALPHA, int: lags)

### `InterestRateSensitivity`

InterestRateSensitivity(obj: ALPHA, str: API_KEY, str: mode)

### `InterestSensitivityDuration`

InterestSensitivityDuration(obj: ALPHA, str: API_KEY)

### `ETFpca`

ETFpca(obj: ALPHA, obj: exchange, int: components, int: window)

### `QuantileQuantile`

QuantileQuantile(obj: ALPHA, obj: BETA, int: window)

### `ReturnRegressions`

ReturnRegressions(obj: ALPHA, int: window)

### `RollingBeta`

RollingBeta(obj: ALPHA, obj: BETA, int: window)

### `ExpLinearRegression`

ExpLinearRegression(obj: ALPHA, obj: BETA, bool: calc_returns, int: period)

### `RegRobustness`

RegRobustness(obj: ALPHA, obj: BETA,int: period, int: window, bool: calc_returns)

### `SessionTurnover`

SessionTurnover(obj: ALPHA, obj: exchange, bool: normalise)

### `VWAP`

VWAP(obj: ALPHA, obj: exchange, bool: normalise)

### `OpenVolume`

OpenVolume(obj: ALPHA, obj: exchange, bool: normalise)

### `CloseVolume`

CloseVolume(obj: ALPHA, obj: exchange, bool: normalise)

### `DecompSTL`

DecompSTL(obj: ALPHA, int: period)

### `RollingSharpe`

RollingSharpe(obj: ALPHA, int: lookback)

### `LinearRegression`

LinearRegression(obj: ALPHA, obj: BETA)

### `CTExplorer`

CTExplorer(obj: ALPHA, obj: BETA, int: lookback, int: multi)

### `Correlation`

Correlation(obj: ALPHA, obj: BETA)

### `Monthly`

Monthly(obj: ALPHA)

### `Seasonality`

Seasonality(obj: ALPHA)

### `Drawdown`

Drawdown(obj: ALPHA, int: window)

### `Distributions`

Distributions(obj: ALPHA, obj: BETA, int: window)

### `RollingReturn`

RollingReturn(obj: ALPHA, int: lookback)

### `ZScore`

ZScore(obj: ALPHA, int: window)

### `MCapTurnover`

MCapTurnover(obj: ALPHA, obj: exchange, int: lookback)

### `WklyMCT`

WklyMCT(obj: ALPHA, obj: exchange, int: lookback)

### `VAR`

VAR(obj: ALPHA, int: window, float: conf)

### `HoldingVAR`

HoldingVAR(obj: ALPHA, int: window, float: conf)

### `WeekdayVolume`

WeekdayVolume(obj: ALPHA, obj: BETA, int: lookback, int: max)

### `VolumePattern`

VolumePattern(obj: ALPHA, obj: BETA, int: lookback, int: max)

### `IntradayPriceRange`

IntradayPriceRange(obj: ALPHA, obj: BETA, int: lookback, int: max)

### `NormalisedAccumulation`

NormalisedAccumulation(obj: ALPHA, obj: feed, int: days, int: norm)

### `VolumeParticipation`

VolumeParticipation(obj: ALPHA, obj: feed, int: days, int: units)
