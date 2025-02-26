# Trading Challenge


## Objective
Create a predictive model that forecasts closing price movements for a diverse range of Nasdaq-listed stocks by using information from the order book and the closing auction.

## Dataset
This dataset contains historic data for the daily ten minute closing auction on the NASDAQ stock exchange. The auction data consists of the following parameters:
* stock_id - A unique identifier for the stock. Not all stock IDs exist in every time bucket.
* date_id - A unique identifier for the date. Date IDs are sequential & consistent across all stocks.
* imbalance_size - The amount unmatched at the current reference price (in USD).
* imbalance_buy_sell_flag - An indicator reflecting the direction of auction imbalance.
  * buy-side imbalance: 1
  * sell-side imbalance: -1
  * no imbalance: 0 
* reference_price - The price at which paired shares are maximized, the imbalance is minimized and the distance from the bid-ask midpoint is minimized, in that order. Can also be thought of as being equal to the near price bounded between the best bid and ask price.
* matched_size - The amount that can be matched at the current reference price (in USD).
* far_price - The crossing price that will maximize the number of shares matched based on auction interest only. This calculation excludes continuous market orders.
* near_price - The crossing price that will maximize the number of shares matched based auction and continuous market orders.
* [bid/ask]_price - Price of the most competitive buy/sell level in the non-auction book.
* [bid/ask]_size - The dollar notional amount on the most competitive buy/sell level in the non-auction book.


## Evaluation
The evaluation is based on the difference i.e Mean Absolute Returns (MAE) between the predicted returns and the actual returns

## Challenges and Considerations
* Combining Order Book and Auction Data: Merging information from both the order book and closing auction data is necessary to make accurate predictions.
* Trading Opportunities: The model should identify potential trading opportunities in the final ten minutes of the trading session.


