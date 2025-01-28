# The Math of Finance

$$\textbf{Theorem 1}: \text{Your money will double every 7 years in the S\\&P500}$$

If you can accept that, congrats. You are one of the minority.

For the danger-seekers, let's dig more into the weeds.

## The Rule of 72

> NOTE: This is just elementary school math, so feel free to skip this section

First, let's talk about how we "derived" the fact above.

We are trying to solve for $t$, where

$\left(1+\frac{r}{100}\right)^t = 2$

$t \cdot \ln\left(1+\frac{r}{100}\right) = \ln(2)$

$t = \frac{\ln(2)}{\ln\left(1+\frac{r}{100}\right)}$

Remembering the power series expansion:

$$\ln(1+r) = \sum_{n=1}^{\infty} \frac{(-1)^{n+1}}{n} r^n = r - \frac{r^2}{2} + \frac{r^3}{3} - \frac{r^4}{4} + \cdots$$

We can see for small values of $r$, terms like $r^2, r^3$ are small and can be approximated as $0$. With that in mind, we can simplify our expression to:

$t = \frac{\ln(2)}{\frac{r}{100}} \approx \frac{100 \times 0.693}{r} = \frac{69.3}{r} \approx \boxed{\frac{72}{r}}$

So you can use 69.3 if you want to be more "precise", but 72 is easier to work with because it has more dividers.

Let's check out some examples, to compare our approximation vs. the exact calculation:

| $r$                    | 1%   | 2%   | 3%   | 4%   | 5%   | 6%   | 7%   | 8%  | 9%  | 10% | 12% | 15% | 20% | 30% | 50% |
| ---------------------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | --- | --- | --- | --- | --- | --- | --- | --- |
| $t$ (yr)               | 72   | 36   | 24   | 18   | 14.4 | 12   | 10.3 | 9   | 8   | 7.2 | 6   | 4.8 | 3.6 | 2.4 | 1.4 |
| $t_\text{actual}$ (yr) | 69.7 | 35.0 | 23.4 | 17.7 | 14.2 | 11.9 | 10.2 | 9.0 | 8.0 | 7.3 | 6.1 | 5.0 | 3.8 | 2.6 | 1.7 |

I added some larger $r$ just to remind that this approximation works better when $r$ is small, so once $r^k$ powers become significant, the rule starts to break down.

## S&P500 Historical Returns

So with the rule of 72 in hand, let's take a look at S&P500 returns.

It's a bit hard to get the dividend data for the S&P500, so I will use a table from [1] that already takes in account dividends reinvested:

| Years Averaged (as of end of December 2024) | Stock Market Average Return per Year (Dividends Reinvested) | Average Return with Dividends Reinvested & Inflation Adjusted |
| ------------------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------- |
| 150 Years                                   | 9.381%                                                      | 6.994%                                                        |
| 100 Years                                   | 10.569%                                                     | 7.405%                                                        |
| 50 Years                                    | 12.393%                                                     | 8.409%                                                        |
| 30 Years                                    | 10.985%                                                     | 8.262%                                                        |
| 20 Years                                    | 10.475%                                                     | 7.719%                                                        |
| 10 Years                                    | 13.316%                                                     | 10.021%                                                       |
| 5 Years                                     | 15.377%                                                     | 10.744%                                                       |

So while we've had a good last few years, in the long term, we have around 10% annualized returns in the S&P500. So we can derive $\textbf{Theorem 1}$ now with:

$$
\begin{equation}
\frac{72}{10\% \text{ S\&P500 annual returns}} \approx 7 \text{ years}
\end{equation}
$$

## The Normal Reactions

So that's it? Why does this article exist? Well, you'd be surprised how many people don't believe the 7 years. I've heard all sorts of reactions:

- 7 years is a lot time, there's no way I can keep my money saved that long
  - Average human life expectancy in the world is 70 years for men [2], and in the US it's higher. You likely have a long life ahead of you.
- 7 years is so short, if it was true wouldn't everyone be rich?
  - Yes, but you'd be surprised how much trouble people have saving, keeping their money still, fighting gambling spirits, etc.
- The doubling doesn't account for inflation!
  - Yes, but check out the inflation adjusted numbers, you're still only looking at 8-9 years for your real wealth to double
- Does this account for the Great Depression? Wars? Dotcom bubble? Great Financial Crisis?

The last one is a good point, let's talk about that more...

## Drawdowns

A **drawdown** is any time a stock price falls from a peak value. So, as an example, if you had a stock price have a peak (can be local or global) at $100, and it falls to $80 in the following weeks, then you've had a drawdown of 20% in the stock.

As alluded to above in the concerns about the stock market, the S&P500 has had some pretty nasty drawdowns. You can check out a [list here courtesy of Wikipedia](https://en.wikipedia.org/wiki/List_of_stock_market_crashes_and_bear_markets).

For some of the notable examples:

- [Great Depression (1929-1932)](https://en.wikipedia.org/wiki/Wall_Street_crash_of_1929): 86% drawdown.
  - Market didn't reach ATH again until 1954.
- [Black Monday (Oct 19, 1987)](<https://en.wikipedia.org/wiki/Black_Monday_(1987)>): 20.4% single day drop (imagine that!)
  - Market recovered by July 1989.
- [Dotcom Bubble (2000-2002)](https://en.wikipedia.org/wiki/Dot-com_bubble): 47.2% drawdown
  - Market reached heights again by 2007...which unfortunately lead to the next crash
- [Great Financial Crisis (2007-2009)](https://en.wikipedia.org/wiki/United_States_bear_market_of_2007–2009): 50% drop
  - Market returned to its peak in March 2013
  - Side note, _The Big Short (2015)_ is a great movie about the GFC
- COVID-19 (2020 Feb-Mar): 34%
  - A miraculous stick save, to get the market back to ATH by August 2020. As President Trump put it, "we're going to have a V-shaped recovery!"

These are just some of the crazy events that have happened in history. And despite the pain then, every time the United States has risen stronger. In the moment, when it rains, it pours. But the cliche of keeping your head up is true, there will always be better days ahead (unless the world ends, then [nothing matters](#does-any-of-this-matter)).

So, if I'm potentially subjecting myself to many years of pain, why would I do that? Well, the market isn't _guaranteed_ to go up. It's just in the long term, it does. And, the price you pay for these returns is the pain you go through during each crash -- _no pain, no gain_.

If you want to have a safer investment, you can invest in short-term bonds, which pending nuclear war and societal collapse, will go up. But their returns are paltry, so why bother in the long term? (obviously, this means if you can't afford to have a drawdown in the short term for some reason, e.g. mortgage, you're getting old, etc, then you should move your money from stocks (risky) to bonds (less risky))

## The Asymmetric Nature of Losses

When your portfolio loses value, the percentage gain needed to recover to its original value is not equal to the percentage lost. In other words, **it's harder to make money with less money**.

If you lose $X\%$, the required gain to recover is:

$$\text{Gain} = \frac{1}{1 - X} - 1$$

This asymmetry grows exponentially as losses deepen:

| Loss | Remaining Capital | Required Gain to Recover | Years at 10% Annual Returns |
| ---- | ----------------- | ------------------------ | --------------------------- |
| 10%  | 90%               | 11.1%                    | 1.1 years                   |
| 20%  | 80%               | 25%                      | 2.3 years                   |
| 30%  | 70%               | 42.9%                    | 3.6 years                   |
| 40%  | 60%               | 66.7%                    | 5.3 years                   |
| 50%  | 50%               | 100%                     | 7.3 years                   |
| 60%  | 40%               | 150%                     | 10.4 years                  |
| 70%  | 30%               | 233%                     | 14.5 years                  |
| 80%  | 20%               | 400%                     | 21.7 years                  |
| 90%  | 10%               | 900%                     | 48.4 years                  |

The last few rows should make your eyes widen, the amount of gain you need to get back to business as normal is a staggering amount. Of course, if you have income, that can help you catch up faster. But if you just consider the original capital, for that to recover, it will take a long, long time.

A common pitfall people fall into is a vicious cycle of:

- After a loss, they take on risk to “make it all back"
- They lose more, which compounds their losses further
- And they want to take on even more risk...because they "have" to in order to make it back

This is [Martingale-esque](<https://en.wikipedia.org/wiki/Martingale_(betting_system)>), also known as "doubling down."

If you find yourself having a very large drawdown that's gonna lead to a margin call or is vastly worse than how the market drawdown is, then a good piece of advice is just to close all your positions because you probably don't know what you're doing.

There is a [good thread about trading down from too much risk exposure from `therobotjames`](https://x.com/therobotjames/status/1759368977594376351). This picture summarizes it pretty well:

![image](https://github.com/user-attachments/assets/78212338-6926-427b-a95a-8e512dc32841)

## The Salesmen

It's a tough world, everyone is trying to make a living. Out and about, you will probably encounter some traveling salesmen.

### Money Managers

Every bank and brokerage offers some sort of wealth management service. The way it works is, they usually come up with some financial goals, like what type of house are you saving for, how many kids you're going to have, if you want to retire early, etc., and then they will give you a template for how to allocate your assets according to what archetypical investor you most resemble. Will they outperform the S&P500 in the long term? Probably not. Will they help you with drawdowns depending on your financial goals? Maybe. But, if you have a long time, your money manager will likely deviate from just the S&P500, because they have to. If they don't, they won't have a job! Unless buying a few shares of $SPY every paycheck is hard, skip someone else charging 1% of your portfolio to treat you to hors d'oeuvres once a year.

### Hedge Funds

Data shows over 80% of hedge funds underperform the S&P500 over 10+ years. One reason for that is most hedge funds charge a 2-and-20 fee model, which means:

- 2% annual fees on assets under management (AUM)
  - 2% annual fee reduces your returns by ~30% over 20 years
- 20% of profits
  - When you play with someone else's money, you're going to take more risk. Think about it from the portfolio manager's point of view. They take a bet that's 10-1 payout. If they make it big? 10x and a big payday. If they lose? They just open another shop.

There are obvious exceptions, such as RenTec, but they are very few.

The other thing to note is that, if you're investing in a Hedge Fund, you're probably not using it to beat the market necessarily. You're likely using it as an investment vehicle that is lower volatility than the market. So, your goal isn't so much capital growth than preservation. Usually, this applies to higher net worth individuals, as for example the 30% potential drawdown from a market crash, is a lot worse on a $20m account than a $200k portfolio.

## "I Can Beat the Market"

There is a popular economic theory called the Efficient Markets Hypothesis (EMH), which says

> Public information is priced in instantly. To beat the market, you need non-public insight.

The classic joke is:

> Two economists are walking down the street. One of them says "Look, there’s a twenty-dollar bill on the sidewalk!" The other economist says "No there’s not. If there was, someone would have picked it up already."

It's ridiculous, right? And, it is. The market is not efficient, but that doesn't mean it's easy to beat it.

My theory for the most common reason people underperform the S&P500 is just the ego that people have, so they believe they can can beat the market. 10% seems so little, I just have to be a bit smarter than the sheep...

While it's true, you can probably do some very, very safe trades and beat the market by a few dollars a year, anything that is worth doing and scales up, is very hard (and conversely, scalping a few dollars a year is probably not worth the effort). Imagine if a fund guaranteed just S&P500 returns + 1% with no additional risk, people would be lining up hands over fist to invest in it.

Here are some common pitfalls I see, a lot I find from Twitter:

### Twitter "furus"

- These guys post predictions about the market. Whether the market will go up or down, if earnings will be good, "rumors" about a company. Their primary goal is engagement or getting you to subscribe to their service.
- They tend to use vague language, like "I sense a rally soon"
- They like to rub things in your face, so aggravate you and make you want to engage with their content
  - These guys are really good at belittling people and developing cult followings
- They will selectively delete tweets that are wrong, so if you go through their timeline, they have a very good hit rate
  - Some will even go through the trouble to post losses just to seem more "genuine"
- In their subscription, which can be a discord channel, chat group, substack, etc., they will post trades, which you can follow
  - Here is a thought experiment: if this "furu" was so good at making money, why are they sharing their alpha with you? The more people know about an edge, the faster it dries up.
  - The other thing to think about, is if someone is earning money from subs, let's say someone is charging $300 a month and has 300 subscribers. They are making $90k/month! They can just buy the S&P500 and be very happy about their future prospects.

### Buying Options

The story goes something like this:

- Stocks move too slow, they only move 1% maybe once a week
- Options move around 10x of what stocks do, 10% ish a day even on calm days
- It seems like options prices seem to move a lot, if I just buy at the right time, I could be up 10% in a day
- And...if I just get it right 7 times in a row, I'd have doubled by money...if I do it for month, I'd have 8x my money. If I do it for a year, I'd be traveling the world in private jets...

Then, the lotto ticket buying begins.

- Calls = stock will go up
- Puts = stock will go down.

But, options are a complex investment vehicle. While understanding what the options contract means, there are so many things about them that people don't understand, e.g., people like to buy options before an earnings to bet if it will go up or down, but options moves can be priced in. In fact, you can actually calculate the implied move of the earnings of a stock just by looking at the ATM strike call and put on the expiration that right after the earnings date.

### Selling Options

What a lot of people realize from buying options, is that it's hard to buy the right one. So, if they are losing so often, why not flip the script and sell options instead?

If you are the house, you can't lose...right?

This is another point people always forget. An option has volatility as part of its price, which means:

$$\text{Every options trade is a }\textbf{volatility trade}$$

The market is usually calm, so the volatility doesn't really become apparent. But just take a look at he $VIX chart for some crash events, or even more mundane ones such as August 5th 2024 Yen carry trade unwind. If you are using margin to sell options, a 300% $VIX spike might send your entire account to 0 instantly.

### Gambling Spirits

Most of us, especially when younger, have a risk appetite, so we _need_ to take on some risk. In that case, there's no point in becoming a closeted gambler, you need some sort of outlet, or else it might manifest in other ways. In that case, a good guidance is to create a new brokerage, only with 10-20% of your total wealth, and you can do whatever you want with it. If it goes to 0, from the [drawdowns analysis](#the-asymmetric-nature-of-losses) we did earlier, we can see a 20% loss would only take around 2 years to get back.

### Closing

Almost nobody can predict the market. The ones that seemingly win time over time, are usually spending many hours a day honing their craft, and also utilizing their many decades of trading experience. Most of these people usually are ready for any situation and nimble, and aren't just smoking a cigar while calling ups and downs for the market. It's not that simple.

## How to Buy the S&P500

Hopefully for most, I've convinced you that investing in the S&P500 is the best way to financial gains and building wealth.

Now, how do you actually buy the S&P500? It's an index, so you can't buy it directly.

Because the index is so popular, you'll actually find a ton of investment products that track its performance, such as ETFs or mutual funds. If you're not sure, just call your broker and they will tell you.

Some common ETFs:

- VOO: [Vanguard S&P 500 ETF](https://investor.vanguard.com/investment-products/etfs/profile/voo)
- SPY: [SPDR S&P 500 ETF Trust](https://www.ssga.com/us/en/intermediary/etfs/spdr-sp-500-etf-trust-spy)
- IVV: [iShares Core S&P 500 ETF](https://www.ishares.com/us/products/239726/ishares-core-sp-500-etf)

And mutual funds:

- VFIAX: [Vanguard 500 Index Fund Admiral Shares](https://investor.vanguard.com/investment-products/mutual-funds/profile/vfiax)
- FXAIX: [Fidelity 500 Index Fund](https://fundresearch.fidelity.com/mutual-funds/summary/315911750)

## Does Any of this Matter?

[`It's just money. It's made up.`](https://www.youtube.com/watch?v=IAqAl292ozs)

## Sources

[1] https://tradethatswing.com/average-historical-stock-market-returns-for-sp-500-5-year-up-to-150-year-averages/

[2] https://data.worldbank.org/indicator/SP.DYN.LE00.MA.IN
