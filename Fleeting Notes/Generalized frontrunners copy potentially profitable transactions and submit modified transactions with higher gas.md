202208011246
Status: 
Tags: #mev

# Generalized frontrunners copy potentially profitable transactions and submit modified transactions with higher gas

- Generalized frontrunners will detect profitable transactions in the mempool
- The bot will copy the transaction code, replace addresses with frontrunner's address and the run tx locally to ensure that the tx results in a profit
- If profitable, frontrunner submits modified tx with replaced address and higher gas price
- Other bots can notice and bid higher txfee causing bidding war to capture arb called a Priority Gas Auction (PGA)






---
# References

