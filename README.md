# Computational_Finance_Survivorship_Bias_Case_Studies
------------------------------------------------

* **Survivorship bias** occurs when the return profile of a portfolio is based solely on existing holdings
* The reasons for a company to cease to exist are varied and may include mergers, acquisitions, corporate restructurings, or bankruptcy
* Including only the “winners” when evaluating portfolio performance will likely skew the data, resulting in overestimating its historical returns.

## Case Study #1 - (20010103 - FOMC Surprise)
Since 2000, your co-worker, Karen, tells everyone at the Portfolio Management weekly meeting that you should follow a MOMENTUM strategy.

 1. "It is very safe!"
 2. "We want to buy what is going up and short what is going down".
 3. "The backtests look great, except we sometimes get big drawdowns"
 4. That is easily solved. I put a stop order at 2% maximum loss and now the strategy only makes money most of the time!

In the midst of the dot-com bust, our favorite QQQ has dropped from the 3/2000 peak. As QQQ crashed, the strategy sold more and more QQQ until it was max short. Your boss starts worrying about a big upswing that can ruin all the accumulated profits.

 1. "What about large intraday moves?"
 2. "Well, all companies report overnight and the FOMC only meets when scheduled, so we only have to watch for those and lessen positions before those times."

20010103 - "In a surprise move, the Federal Reserve slashed short-term interest rates Wednesday and signaled it is ready to make further cuts to keep the U.S. economy from sliding into a recession."

https://money.cnn.com/2001/01/03/economy/fed/

Did the stop work?
* Connect and load data to MongoDB.
* Collection: CaseStudyDb
* Search for: 
 1. Symbol = QQQ
 2. Date = 20010103

Other fields are:

c - List of close prices for returned candles.

h - List of high prices for returned candles.

l - List of low prices for returned candles.

o - List of open prices for returned candles.

s - Status of the response. This field can either be ok or no_data.

t - List of timestamp for returned candles.

v - List of volume data for returned candles.

## Case Study #2 - 20080919 SEC Halts Short Selling of Financial Stocks to Protect Investors and Markets
In 2008, the SEC did something that no one expected. It halted short selling in a list of financial stocks. If no one can short, are price drops impossible?

https://www.sec.gov/news/press/2008/2008-211.htm

Announced on 20080919 pre-market, is that a good day to BUY?
* Connect and load data to MongoDB.
* Collection: CaseStudyDb
* Search for: 
 1. Symbol = XLF
 2. Date = 20080919

Other fields are:

c - List of close prices for returned candles.

h - List of high prices for returned candles.

l - List of low prices for returned candles.

o - List of open prices for returned candles.

s - Status of the response. This field can either be ok or no_data.

t - List of timestamp for returned candles.

v - List of volume data for returned candles.


## Case Studies Walkthrough
See step-by-step analysis in codes and comments here: https://github.com/AmberHou1230/Computational_Finance_Survivorship_Bias_Case_Studies/blob/main/Beautiful_Soup%2C_MongoDb%2C_Survivorship_bias.ipynb

### Web Parsing - iShares, StockAnalysis, Finviz

* iShares is one of the biggest providers of ETFs. It is a subsidiary of BlackRock.
* Why do we need StockAnalysis and Finviz after parsing iShares? iShares is just one company and doesn't have all the ETFs. 

* Additional notes on ETFs:
  *  The upside of mutual funds is diversification. What's the downside? Buying and selling frequently generate taxable activities, which then get passed onto the shareholders.
  *  ETFs get rid of this downside (because of a tax loophole called an exchange.)
  *  In the U.S., if I buy a house and live in it for 3 to 5 years and then sell it, I will have some amount of capital gain. But if I buy a second house within a 12-month period, I don't have to pay a capital gain tax. I'll just be rolling over what the tax bill would be.
  *  Ideally one day I sell everything and I pay a big tax bill many many years from now. But nobody sells everything. They just die. In the U.S., you don't pay capital gain tax when you die, you pay a death tax :) In other words, you just keep deferring your capital gain until you don't need to pay anymore. 
  *  When I sell my first house and buy my second house, it is called an exchange, not a trade. a.k.a. no taxable realization. So somebody thought well, we can use that loophole and apply it to the stock market. Instead of buying and selling stocks, ETFs are **exchanging** stocks, therefore when you invest in an ETF, there's no tax. 
  *  If you want to be a passive investor, there is no reason for you to invest in mutual funds anymore, you just pick ETF. 
