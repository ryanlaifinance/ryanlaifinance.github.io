# Micron benefits from a strong US dollar. Should you hedge that away?

**Course** FINS3616 International Business Finance, UNSW, T1 2026
**Tools** Excel, FactSet
**Result** 90/100 (HD)

---

## The question

Micron Technology is a US semiconductor company headquartered in Idaho. The textbook
expectation for a US multinational is a negative FX beta: it earns revenue abroad, so a
stronger dollar hurts it. Coca-Cola and Procter & Gamble behave that way.

Micron does not. I measured its currency exposure over 280 months and got a positive FX
beta, which means a stronger dollar helps it. The question then becomes whether an
investor holding Micron should hedge that exposure at all, and what it costs if they do.

## Data and method

I ran a two-factor regression of Micron's monthly excess return on the market excess
return and the return on the ICE US Dollar Index, using 280 monthly observations from
FactSet. Adding DXY alongside the market factor separates currency sensitivity from
Micron's general cyclicality, which matters here because memory is a highly cyclical
business and the two effects would otherwise be confounded.

I then checked the regression against Micron's own disclosures rather than trusting the
coefficient on its own. The FY2018 and FY2024 10-K filings describe where the revenue and
the costs actually sit.

For the hedge I used ICE US Dollar Index futures: notional of $1,000 times the index
level, cash settled quarterly, so four front-quarter contracts cover a one-year holding
period.

## Results

**Chart 1.** Micron monthly excess return against DXY return, with the fitted line.

| | Estimate | t-stat |
|---|---|---|
| Market beta | 1.825 | 10.70 |
| FX beta | +1.184 | 3.55 |
| Adjusted R² | 0.288 | |

Both coefficients are significant well below the 5% level, and the joint F-statistic of
57.35 confirms they matter together.

Statistical significance is not the same as economic significance, so I scaled each
coefficient by the volatility of its factor. A one standard deviation move in the market
(4.35%) moves Micron by 7.93%. A one standard deviation move in DXY (2.22%) moves it by
2.63%. The market factor is about three times more economically important, even though
both coefficients are significant.

The 10-K filings explain the sign. Micron's functional currency is the US dollar and the
substantial majority of its sales are transacted in dollars, but a significant portion of
its manufacturing cost base sits in yen, Taiwan dollars and Singapore dollars. Revenue in
USD, costs in Asian currencies. A stronger dollar compresses the cost base while leaving
revenue intact, which is exactly the exposure the regression picked up.

## Sizing the hedge, and what it costs

For a USD 1M equity position, the FX beta gives an effective DXY exposure of $1,184,300.
At a December 2024 index level of 108.49, each contract carries a notional of $108,490,
which is 10.92 contracts, rounded to 11. The beta is positive, so the hedge is a short.

I then ran the position through a stress scenario where DXY rises from 90 to 100 and the
stock gains 20%, with 0.5% transaction costs on both legs.

| | |
|---|---|
| Stock, net of costs | +$189,000 |
| Futures leg | -$130,650 |
| Net payoff | +$58,350 |

The hedge worked. It also consumed 69% of the gain. That is the real finding: for an
investor whose FX exposure is a tailwind rather than a risk, a full futures overlay is an
expensive way to buy certainty.

## What I concluded

Hedging Micron with DXY futures is defensible if the mandate is to isolate the equity
view, but it is a bad default. The cheaper route is diversification, so I tested it.

Caterpillar is the classic exporter: foreign currency revenue, dollar cost base. It prices
out at an FX beta of -0.765. Paired with Micron in equal weight, the portfolio FX beta
falls to +0.210 and stops being significant at the 5% level.

**Chart 2.** FX beta for Micron, Caterpillar and the combined portfolio.

That is an 82% reduction in currency exposure. Micron alone moves ±2.63% on a one sigma
DXY move; the portfolio moves ±0.47%. Same result as the futures overlay, no ongoing cost,
no margin.

## What I would do differently

I estimated a single FX beta across 280 months, but Micron's manufacturing footprint
changed a lot over that period. A rolling window would show whether the exposure is stable
or drifting, which matters if you are sizing a hedge off it today.

DXY is also a blunt instrument here. Micron's costs sit in yen, Taiwan dollars and
Singapore dollars, and DXY is weighted heavily toward the euro. A currency basket matched
to the actual cost base would hedge the exposure the filings describe, rather than a proxy
for it.

<!-- TK: confirm this reflection matches what you actually think. Replace if not. -->
