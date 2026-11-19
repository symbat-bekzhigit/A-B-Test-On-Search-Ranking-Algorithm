# A/B Testing: Evaluating a Search Ranking Algorithm

## Project Overview

This project evaluates whether a new search ranking algorithm improves booking conversion rates without negatively affecting the time customers need to complete a booking.

The analysis uses A/B testing methodology to compare a control group with a variant group and translate statistical findings into a product rollout recommendation.

## Business Problem

An online travel agency is considering replacing its existing search ranking algorithm. The new algorithm should increase booking conversions while maintaining or improving the booking experience.

The objective is to determine whether the experiment provides sufficient evidence to support a full rollout.

**Rollout Decision Criteria:**

A full rollout is recommended only when both conditions are satisfied:

1. **Primary metric:** The conversion rate improvement is statistically significant (p-value below 0.10) and the effect is positive.
2. **Guardrail metric:** The difference in time to booking is either statistically insignificant (p-value above 0.10) or the effect is favorable (a decrease in booking time).

## Key Metrics

- **Primary metric:** Session conversion rate — the proportion of sessions resulting in a booking.
- **Guardrail metric:** Time to booking — the average time between session start and booking.
- **Experiment sanity check:** Sample Ratio Mismatch (SRM) — whether the observed group allocation is consistent with the intended 50/50 split.

## Methods & Tools

**Statistical methods**
- Chi-square goodness-of-fit test for SRM.
- Two-proportion Z-test for conversion rates.
- Two-sample t-test for time to booking.
- Relative effect size calculations.
- Hypothesis testing at a 10% significance level.

**Tools**
- Python
- Pandas
- SciPy
- Pingouin
- Statsmodels
- Matplotlib

## Key Results

- Conversion rate increased from 15.92% to 18.19%.
- Relative conversion improvement: 14.26%.
- Conversion difference was statistically significant (p = 0.0002).
- Average time to booking decreased by 0.8%, with no statistically significant difference (p = 0.5365).

## Recommendation

The experiment meets the predefined full-rollout criteria based on the analyzed session-level metrics.


## Limitations

- The session-level statistical tests may not account for potential correlation between sessions from the same user.
- The allocation check compares session counts between groups, while the experiment assignment is assumed to be performed at the user level.

These limitations should be considered when interpreting the results and planning future experiments.
