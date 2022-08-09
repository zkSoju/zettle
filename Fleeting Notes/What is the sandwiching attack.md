202208090008
Status: 
Tags: #mev

# What is the sandwiching attack
- Victim trades asset X for Y in a large increment
- Bot sniffs order and buys a significant amount of asset Y because the victims order will raise the price of Y
- Bots order also raises the price of asset Y and increases the slippage
- Price slippage is the change in price of asset during a trade
	- Expected slippage is expected increase/decrease based on volume traded and liquidity
	- Unexpected could be caused by sandwich attack
- zkSNARKs usage? But high gas cost
- The bad
	- User may YOLO into shitcoin with high slippage in order to fill order but would end up receiving amount magnitude lower than expected in absence of sandwich attack
- The good 
	- Sandwich bot operator moves economic system towards Nash Equilibrium
	- Market meets consumer's maximum willingness to pay while extracting value for operator
- Retail markets use https://www.bloomberg.com/opinion/articles/2021-12-08/what-does-payment-for-order-flow-buy



---
# References

