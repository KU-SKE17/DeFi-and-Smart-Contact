# DeFi and Smart Contact <!-- omit in toc -->

- grade = project
- solidity project (group 2 people)

## Table of Contents <!-- omit in toc -->

- [week1 Time and Money](#week1-time-and-money)
  - [Compounding](#compounding)
    - [Future Value](#future-value)
    - [Effective vs Nominal Rates](#effective-vs-nominal-rates)
    - [Present Value](#present-value)
  - [Discounted Cash Flows (DCF)](#discounted-cash-flows-dcf)
    - [Simple Bond](#simple-bond)
    - [Stock Valuation](#stock-valuation)
    - [Other Assets](#other-assets)
  - [Valuation by Comparables](#valuation-by-comparables)
    - [Assumptions for Comps](#assumptions-for-comps)
    - [Other Comps](#other-comps)
  - [Comps VS DCF](#comps-vs-dcf)

## Notebooks <!-- omit in toc -->

All calculation detail will be in the notebooks

- [Notebook1](week1.ipynb)

## week1 Time and Money

`Current Value better than Future Value`

Because:

1. Opportunity Cost
   - better economic growth
   - (loose the opportunity to invest)
2. Inflation
   - gov prints more money
   - (time goes by, money later worth less)
3. Risk
   - wars, disasters, etc.
   - (I may not be here to use the money)

### Compounding

- Effective -> ได้ดอกเบี้ยทบกันไปเลื่อยๆ
- Calculate -> `Future Value`

#### Future Value

    FV = PV(1+r)^t

- FV = Future Value
- PV = Current Value
- r = Interest Rate
- t = deration (years)

#### Effective vs Nominal Rates

    Reff = (1+(Rnom/n))^n

- Nominal = periodic rate times the number of periods
- Effective = nominal rate + compounded rate
- ex.
  - Nominal rate
  - 6% per year = (6%/12) = 0.5% per month
  - Effective rate
  - (1+0.5%)^12 = 6.17% per year

`Effective Rates > Nominal Rates`

#### Present Value

    PV = FV/(1+r)^t

$100 in next 50 years is nothing. if discounted(r) = 10%

### Discounted Cash Flows (DCF)

- method of valuing an investment
- discounts all cash flows back to present value
- investors buy different assets to earn a return and use the money later
- investment value -> (When/How much) cash is coming in?

#### Simple Bond

- Bond Worth = total worth of payment each year
- payment each year = payment - discounts rate
- ex.
  - simple bond of 3,000 with annual payment of 250 for 5 years, discount rate 7%
  - bond worth (Present Value) = 3,164 (233.6 + 218.4 + 204.1 + 190.7 + 2,317.2)

#### Stock Valuation

- stock analysts
- ex. ถ้าจะถือหุ้นไว้ 5 ปี ปันผลคุ้มไม

#### Other Assets

- Real Estate
- Mergers and Acquisitions
- Derivatives

### Valuation by Comparables

- Practitioners often refer to `comps`
- Comparable transactions or prices
- Quick, easy, and dangerous! -> what is your assumptions?

#### Assumptions for Comps

1. You can identify close comparables
2. You have a value–relevant ratio
3. The market values comps similarly

```txt
Asset Price = (Price/Attribute) * Attribute
```

- Asset Price = price of your asset
- Attribute = your attribute
  - `P/E ratios`
  - Earnings Yield
  - Dividend Yield
  - Return on Assets
  - EBITDA multiples
  - etc.

`P/E ratios` (Price–to–earnings ratio)

- popular
- use to compare 2 cost/deal btw 2 places
- ex. Home Depot vs Lowes

#### Other Comps

- Return on Assets or Equity (ROA/ROE)
- Return on invested capital (ROI)
- Dividend yield
- PEG ratio (P/E ratio over Growth in E)

### Comps VS DCF

- Both can provide useful information
- Executed correctly, both are valid
- Comps often used (and abused) in practice
- Both require forecasts
- DCF is more appealing in theory and more accurate, but requires much more work
- Comps can be a good quick-and-dirty valuation, but be
  careful!
