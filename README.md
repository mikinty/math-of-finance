# The Math of Finance

$$\textbf{Theorem 1}: \text{Your money will double every 7 years in the S\&P500}$$

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
  - Average human life expectancy in the world is 70 years for men, and in the US it's higher. You likely have a long life ahead of you.
- 7 years is so short, if it was true wouldn't everyone be rich?
  - Yes, but you'd be surprised how much trouble people have saving, keeping their money still, fighting gambling spirits, etc.
- The doubling doesn't account for inflation!
  - Yes, but check out the inflation adjusted numbers, you're still only looking at 8-9 years for your real wealth to double
- Does this account for the Great Depression? Wars? Dotcom bubble? Great Financial Crisis?

The last one is a good point, let's talk about that more...

## Sources

[1] https://tradethatswing.com/average-historical-stock-market-returns-for-sp-500-5-year-up-to-150-year-averages/

[2] https://data.worldbank.org/indicator/SP.DYN.LE00.MA.IN
