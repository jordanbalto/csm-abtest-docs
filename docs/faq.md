# FAQ
## What is DS's specific methodology for conducting the test?
- We use statistical modeling, specifically [mixed modeling](https://en.wikipedia.org/wiki/Mixed_model) to estimate the 
marginal impact of Balto usage while simultaneously controlling for as many potential confounding factors as possible.
## Why use a statistical model instead of comparing group level averages?
- Statistical (regression) models can account
  for other sources of variation in the KPI of interest besides Balto/non-Balto 
  group assignment.
- Models can account for time explicitly.
- Group assignment may not be random or group size may be too small for randomization
  to produce groups that are statistically equivalent. Controlling for some group differences
  leads to a higher level of confidence that the Balto effect is really due to Balto and not some
  other source of variation.
- Regression models avoid unnecessary aggregations. As a general rule, statistical analyses
  should rely on as much relevant information as possible. Computing group-level or
  time-level statistics removes information about variation in performance across agents or time periods.
- Regression models can measure the magnitude of the Balto effect, formally test whether it is statistically different
  from zero, and compute confidence intervals to address uncertainty.

## How much data do I need?
- As a general rule of thumb, more data is always better. When conducting an A/B test or any experiment, sample size
can be thought of as a 'net' to catch statistically significant effects. The larger the sample size, the smaller the holes
in the net are. On the converse, when sample size is small the holes in the net are large. The implication of this is that a
larger sample size is better because it enables us to catch a smaller effect. If sample size is not large enough, the holes
in the metaphorical net may be too large to observe the occurrence of a  small but significant effect. 