# A/B Testing: Evaluating a New Search Ranking Algorithm

## Project Overview

This project evaluates whether a new search ranking algorithm improves booking conversion rates without negatively affecting the time customers need to complete a booking.

The analysis uses A/B testing methodology to compare a control group with a variant group and translate statistical findings into a product rollout recommendation.

## Business Problem

An online travel agency is considering replacing its existing search ranking algorithm. The new algorithm should increase booking conversions while maintaining or improving the booking experience.

The objective is to determine whether the experiment provides sufficient evidence to support a full rollout.

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
- Relative conversion improvement: 14.22%.
- Conversion difference was statistically significant (p = 0.0002).
- Average time to booking decreased by 0.79%, with no statistically significant difference (p = 0.5365).

## Recommendation

The experiment meets the predefined full-rollout criteria based on the analyzed session-level metrics.


## Limitations

- Multiple sessions from the same user may violate the independence assumption of the session-level tests.
- The analysis population is limited to sessions successfully matched to experiment users.
- The guardrail analysis includes sessions with a booking because time to booking is unavailable for non-converting sessions.