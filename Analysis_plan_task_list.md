## Description and status of tasks in our planned analysis strategy
<br>
*A note about the meaning of the symbols used in the task list below:*
* *denotes an item not yet undertaken.*
- [ ] *denotes an item completed generically but not yet applied to the final data.*
- [X] *denotes an item sufficiently completed.*

<br>
### Initial input data
The following types of input data will be required:
* lists of company stock symbols and names (potentially including aliases).
* lists of search terms believed to be potentially relevant for foreshadowing stock price moves (esp. losses).


<br>
### Intermediate derived data
The following data are expected to be developed as part of the analysis process:
* lists of many specific company+keywords queries to run through Google Trends.
* time series of relative company+keywords search query frequency from Google Trends.
* vector of bins of serach query frequency at different (average) lags.
- [ ] time series of stock closing prices from Yahoo Finance.
- [ ] time series of calculated stock returns over *n* days.
* binary time series of 1s for high magnitude losses and 0s elsewhere.
* ...


<br>
### Anticipated tasks
The following types of tasks are expected to be needed:
- [X] develop functions to algorithmically pull results from Google Trends and Yahoo Finance.
* review the academic literature related to this phenominon -- through this we will develop the list of search keyworks believed to be potentially relevant for foreshadowing stock price moves (esp. losses).
* combine the lists of company names/aliases/stock symbols with the lists of potential search keyworks -- through this we will develop a list of specific company+keywords queries to run through Google Trends.
- [ ] use the pytrends third-party API to run each of these company+keywords queries through Google Trends -- this will result in time series of relative query frequency.
- [ ] use our custom functions to pull data from Yahoo Finance for the list of stock symbols -- this will result in time series of adjusted closing prices.
- [X] develop functions to calculte (lognormal) returns over the preceding *n* days -- this will result time series (*n* elements shorter than the original time series of closing prices) of stock returns.
* develop functions that filter our low-amplitude, high-frequency losses as daily noise events, and keep only the less frequent, greater magnitude events that we are trying to predict -- this will result in binary time series of 1s for high magnitude losses and 0s elsewhere.
* each daily return for a stock can now be associated with a vector of search term frequencies at various lags *h* days previously. 
* create bins of lags and a use their average (or other basis function) to represent that lag.
* find the highest correlation between search term frequency at past lags (or avg from bins of lags) for high magnitude stock losses.
* ...


<br>
### Parameter choices
The folowing parameter & modeling choices will need to be made, based on either statistical fitting or playing with the various models and resuls to identify parameter settings that seem to respond well and yield interesting results:
* choice of which companies/stocks to include.
* choice of which market-related search keyworks to include.
* choice of *m* days over which to request Google Trends data; frequency results will be normalized of this range.
* choice of *n* days over which to calculate trailing returns (could also be an optimized result).
- [X] choice to focus on stock losses insteaad of gains.
* choice of magnitude of losses to filter out as normal fluctuations vs to retain and try to predict (e.g., above 1/2/3 sigma?).
* choice of maximum time period over which to assess lags of different length between.
* choice of bin size (if any) when grouping bins for prediction.
* ...


<br>
### Results and outputs
* identification of optimal *n* days over which to calculate trailing returns (could also be a parameter choice).
* identification of optimal lag(s) for correlating increase search frequency with later, corresponding stock price movement.
* identification of optimal keywords for which to monitor for future potential stock price moves.
* summarization of and plots showing degree of correlation between past search term frequency and stock price moves.
* ...
