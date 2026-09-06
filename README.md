# Where Should the Tube Get Air-Conditioning First?

A statistical analysis of London Underground line temperatures, used to
recommend which line should get a pilot air-cooling system.

## The business problem

London Underground lines get hot, especially in summer, and installing
air-cooling systems across the whole network at once isn't realistic.
Before spending the money, it makes sense to pilot the system somewhere
first - the question this project answers is: **which line should that
be?**

## What this project does

- Checks the data for missing values and realistic value ranges before
  drawing any conclusions
- Excludes "Sub-Surface Lines" from the comparison, since they're built
  closer to the surface than the rest of the network and have a distinct
  temperature profile that isn't comparable to the deep-level lines
- Summarises mean, standard deviation, and range of temperature by line
- Visualises the temperature distribution across all lines
- Runs a t-test to check whether the hottest line's temperature advantage
  is statistically real, not just a difference in averages that could be
  chance
- Repeats that test specifically for summer months, since that's when
  passenger discomfort actually matters most
- Translates the statistical findings into a clear recommendation

## Structure

The report is written in two sections on purpose:

- **Section 1** is the technical analysis - the code, the statistical
  tests, the reasoning at each step
- **Section 2** covers the same findings in plain language, written the
  way you'd actually explain it to a manager who doesn't code

## Files

| File | Purpose |
|---|---|
| `underground_analysis_portfolio.Rmd` | The full analysis |
| `underground_analysis_portfolio.html` | The knitted report |
| `Underground.csv` | Monthly average temperature data by London Underground line |

## How to run it

```r
install.packages(c("tidyverse", "gridExtra", "kableExtra"))
```

Put all three files in the same folder, open
`underground_analysis_portfolio.Rmd` in RStudio, and click Knit.

## Key result

Bakerloo has the highest mean temperature of any line (26.82°C) and the
highest average summer temperature (28.74°C), with individual readings
reaching as high as 32.41°C. A t-test confirms Bakerloo runs significantly
hotter than Central (the next-warmest line) across the full year - though
that specific gap narrows to statistically insignificant during summer
months alone. Bakerloo remains the strongest candidate for the pilot: it
has the highest overall average and some of the most extreme individual
readings on the network, giving the clearest test of the system under the
most demanding conditions.
