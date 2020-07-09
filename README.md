## 2020 Summer internship

## Goals:
- Learn how the stock market moves and how it changes throughout the day.
- Learn how to setup thinkorswim to your personal liking (ie. chart layouts, color coding)
- Gain an understanding for day trading with Thinkorswim.
- Learn how to write code with the built in language thinkscript.
- Write your own studies with the skills you learned from thinkscipt.


## Getting into Thinkorswim: 
- We began with watching a series of udemy videos that taught us the basics of Thinkorswim.
- Udemy videos: https://worcester.udemy.com/organization/home/
- We learned about candles, how to recognize a possibly good trade, and to actually make a trade.
- We also learned about the different order types that could be made when we want to make a trade.
- Then we read through the Thinkorswim learning center were we learned what each tabs purpose was on the thinkorswim app.
- Thinkorswim learning center: https://tlc.thinkorswim.com/center/howToTos/thinkManual/Getting-Started
- We then learned how to personalize our charts and import studies.


## Begin trading:
- We started off with 200k and began some group trading to gain an understanding of how the stock market moves throughout the day.
- We checked news articles each morning to see the predictions for a stock that day.
- We also watched a couple Youtube videos in our free time to help improve out knowledge: https://www.youtube.com/watch?v=YwvcyLca2Dk
- Once we felt confidant in our ability to trade we began our 40k challenge were we were tasked to trades with a low amount of money.
- We then began creating studies of our own and using them in our trading.
- With our new studies we began a 60k challenge to see who could earn the most with their study.

## Learning Thinkscript:
- Thinkscript is a built in language for Thinkorswim.
- Using the Thinkorswim learning center we went through the chapters and learned how to code with thinkscript.
- Thinkscript learning center: https://tlc.thinkorswim.com/center/reference/thinkScript
- We did some coding as a group to gain an understanding to how it works.
- We then created code that would indicate when to buy or sell a stock.

## Learning Resources:
- This website had some great sample code to test: https://funwiththinkscript.com/category/example-code/
- This was a good source of news on stocks: https://finance.yahoo.com/
- These videos are really informative on trading and how the stock moves: https://www.youtube.com/user/TradenetGlobalUK

## Graphs Examples:
- ![Screen Shot 2020-07-09 at 11 13 04 AM](https://user-images.githubusercontent.com/55325202/87058566-3c79d180-c1d6-11ea-9f52-91b473a42be5.png)

- <img width="960" alt="2020-07-09" src="https://user-images.githubusercontent.com/55325202/87058829-9084b600-c1d6-11ea-8a08-5cdacb24b3eb.png">

- This graph has a study attatched that adds a space between candles: ![Screen Shot 2020-07-09 at 11 26 05 AM](https://user-images.githubusercontent.com/55325202/87059221-0721b380-c1d7-11ea-8ca5-0b22b61b0dda.png)


## Thinkscript Examples:
- This code makes it so the background will change to two different colors when the VWAP line has been crossed:
        
        def crossOfVWAP = open < close and open < vwap and close > vwap;
        def firstCrossOfVwap = CompoundValue(1, if close < vwap then 0 else 1, 1);
        plot signal = firstCrossOfVwap and !firstCrossOfVwap[1];
        AssignBackgroundColor(if signal then Color.LIGHT_GREEN else Color.DARK_RED);
* This is what the graph would look like given the code above: ![Screen Shot 2020-07-09 at 11 37 36 AM](https://user-images.githubusercontent.com/55325202/87060516-9ed3d180-c1d8-11ea-9a9c-f601f59deba1.png)

- This code shows the best buy and sell sugestions and the daily simple moving average:
        input price = close;
        input length = 20;
        def avg = Average(price, length);
        AddOrder(OrderType.BUY_AUTO, price crosses above avg, open[-1], 100, Color.green, Color.green, “Buy”);
        AddOrder(OrderType.SELL_AUTO, price crosses below avg, open[-1], 100, Color.RED, Color.RED, “Sell”);
        AddLabel(yes, if close > Average(close, 20) then "Uptrend" else "Downtrend",if close > Average(close, 20) then Color.GREEN else Color.RED);
        AddLabel(yes, Average(close, 20), if close > Average(close, 20) then Color.GREEN else Color.RED);
* this is what the graph would look like given the code above: <img width="960" alt="2020-07-09 (1)" src="https://user-images.githubusercontent.com/55325202/87060693-d6db1480-c1d8-11ea-899d-70d93e60213e.png">
