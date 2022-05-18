# Homework 6

##### 1. What encourages someone to monitor health factors of any accounts and possibly become a liquidator?

Liquidators get collateral as reward of monitor health factors of accounts.

##### 2. Why do on-chain lendings/borrowings tend to be over-collateralized?

Because the number of debt borrowers can take on is typically inferior to the security deposit in value.

##### 3. If I use 2 ETH as a collateral to borrow USDT right now from a lending platform that has a liquidation factor of 0.6, what is the maximum USDT amount I can borrow? Is it recommended that I borrow to that maximum limit and why?

```
HF = VC x LT / VD
1 = 5592 USDT x 0.6 / VD
VD = 3355.2 USDT
```

Max USDT can be borrowed is 3355.2 USDT

Not recommended, because it possible for health factor falls below 1

##### 4. What exactly is a flash loan and what are some of its uses?

Flash loan is an uncollateralized lending protocol, used in decentralized finance networks without passing intermediaries.

It can be use for Farming or attack DeFi, using system gaps to create greater price differentials.

##### 5. Explain the mechanics used in each of the following stable coins to maintain its peg to USD?

- USDT: gives 1 USD credit to user for every deposition
- DAI: has algorithms to balance its price, active when its value went below an US dollar
- Ampleforth: has countercyclical algorithms to to balance its price with another cryptocurrency, AMPL

##### 6. Why cannot a miner take a role as an oracle?

Because some miners are unreliable.

##### 7.Assume an oracle committee has five nodes (A, B, C, D, E) 1/1 and it is agreed to report the median value. Node E is a malicious node, and E observes the following values from the other four nodes (A: 1000, B: 1010, C: 1020, D: 1030). What are the upper and lower bounds of the aggregated value to which E can manipulate?

upper = 1010

lower = 1020

##### 8. Assume an oracle committee has five nodes (A, B, C, D, E) 1/1 and it is agreed to report the median value. Nodes D and E collaborate to manipulate the aggregated oracle update, and the other three nodes report the following values (A: 1000, B: 1010, C: 1020). What are the upper and lower bounds of the aggregated value to which D and E can manipulate?

upper = 1000

lower = 1020

##### 9. Why do we say that price reports from DEXes have crypto-economic oracle property?

Because DEXes use various pairs of asset for trading. So its exchange rate tends to reflect to its real price.

##### 10. If we can settle everything on the settlement date in a futures contract, why do we need a mark-to-market daily settlement?

Because the locked price mechanism is placed only in order to reduce counterparty and credit risk, it dosen't change the fact that exchange members are obligated to clear their trades at the end of each day.

##### 11. Can futures exchanges go broke if they are not careful with margin requirement? Explain how and give a concrete example.

The futures exchanges definitely can broken if they are not careful with margin requirement. For example:

- item price = $100
- margin set at 10% of the item price (margin = $10)
- but then the price decreased 20% by the market (item price = $80, margin = $8)
- sellers will lost their profit (since the selling price decreased)
- buyers will need to pay for the remain balance of the margin requirement (remain = $2)

##### 12. Calculate the amount of risk-free profit to be had in the following situation: Spot price of Platinum is $1,000/oz, 1-year future settlement price is $1,200/oz Borrowing interest rate is 10% per year, Storage cost: $50 per oz. per year

```
FV = (PV x (1 + r)^t) + cost
1320 = (1000 x (1 + r)^1) + 50
r = 0.27
```

##### 13. What are perpetual futures contracts and why are they popular wit cryptocurrencies?

The perpetual futures contract is an agreement to non-optionally buy or sell an asset at an unspecified point in the future.

Because they are cash-settled, no pre-specified delivery date, can be held indefinitely, and no expiration.

##### 14. What is the relationship between the spot price of a crypto asset and its perpetual futures price and how is this relationship maintained?

Both the spot price and the futures price are quotes for a purchase contract. The spot price is a current cost to purchase, but the perpetual future is a advance cost set by seller and buyer.

##### 15. How are perpetual futures traded on dYdX differ from those traded on Binance?

- dYdX: realtime traded, calculate using funding fee
- Binance: 8 hours delay traded, calculate using the average price of asset across the major exchanges
