## Description and status of tasks in our planned analysis strategy

<br>

*A note about the meaning of the symbols used in the task list below:*
- [ ] *denotes an item completed not yet completed or applied to the final data.*
- [X] *denotes an item sufficiently completed.*

<br>

### Initial input data
The following input data form the basis for this analysis:
- [X] lists of company stock symbols and names (potentially including aliases).
- [X] lists of search terms (or categories of terms) believed to be relevant for foreshadowing stock price moves (esp. losses).


<br>

### Intermediate derived data
The following data developed during the analysis process:
- [X] company, keywords, & category queries to run through Google Trends.
- [X] time series of relative company+keywords search query frequency results from Google Trends.
- [X] time series of stock closing prices from Yahoo Finance.
- [X] time series of calculated stock returns over *n* days.
- [X] binary time series of 1s for high magnitude losses and 0s elsewhere (to filter low-amplitude, high-frequency events).


<br>

### Analysis tasks
The following types of tasks are involved in this analysis:
- [X] develop functions to algorithmically pull results from Google Trends and Yahoo Finance.
- [X] review the academic and grey literature related to this phenominon -- this we will develop potential lists of search keyworks believed to be potentially relevant for foreshadowing stock price moves (esp. losses).
- [X] combine the lists of company names/aliases/stock symbols with the lists of potential search keyworks -- this will support development of lists of specific company+keywords queries to run through Google Trends.
- [X] use the pytrends third-party API to run each of these company+keywords queries through Google Trends -- this will result in time series of relative query frequency.
- [X] use our custom functions to pull data from Yahoo Finance for the given stock symbols -- this will result in time series of adjusted closing prices.
- [X] develop functions to calculte (lognormal) returns over the preceding *n* days -- this will result time series (that are *n* elements shorter than the original time series of closing prices) of stock returns.
- [X] develop functions that filter our low-amplitude, high-frequency losses as daily noise events, and keep only the less frequent, greater magnitude events that we are trying to predict -- this will result in binary time series of 1s for high magnitude losses and 0s elsewhere.
- [X] each daily return for a stock can now be associated with a vector of search term frequencies at various lags *h* days previously. 
- [X] explore different bin and lag sizes and a use their average (or other basis function) for summarizing prior search intensity.
- [X] find the highest correlation between search term frequency at past lags (or avg from bins of lags) for high magnitude stock losses.


<br>

### Parameter choices
The folowing parameter & modeling choices will need to be made, based on either statistical fitting or playing with the various models and resuls to identify parameter settings that seem to respond well and yield interesting results:
- [X] choice of which companies/stocks to include.
- [X] choice of which company name-related search keyworks to include.
- [X] choice of categories to pull trends data from.
- [X] choice of *m* days over which to request Google Trends data; frequency results will be normalized of this range.
- [X] choice of *n* days over which to calculate trailing returns (could also be an optimized result).
- [X] choice to focus on stock losses insteaad of gains.
- [X] choice of magnitude of losses to filter out as normal fluctuations vs to retain and try to predict (e.g., above 1/2/3 sigma?).
- [X] choice of maximum time period over which to assess lags of different length between.
- [X] choice of bin size (if any) when grouping bins for prediction.


<br>

### Results and outputs
* identification of optimal *n* days over which to calculate trailing returns (could also be a parameter choice).
* identification of optimal lag(s) for cross-correlating search frequency with stock price movement.
* identification of optimal keywords for which to monitor for future potential stock price moves.
* summarization of and plots showing degree of correlation between past search term frequency and stock price moves.
