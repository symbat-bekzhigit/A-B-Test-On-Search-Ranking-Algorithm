# A/B Testing: Evaluating a New Search Ranking Algorithm

## Executive Summary

### Business Objective

An online travel agency is considering introducing a new search ranking algorithm to improve booking conversion rates. The Product team wants to determine whether the new algorithm increases conversions without negatively affecting the booking experience.

The objective of this analysis is to evaluate the experiment results and provide a data-driven recommendation on whether to fully roll out the new algorithm.

### Approach

I analyzed session-level booking data and user-level experiment assignments to compare the control group (existing algorithm) against the variant group (new algorithm).

The analysis included:

- **Sample allocation check:** A chi-square goodness-of-fit test to assess whether session counts were consistent with the expected 50/50 split.
- **Primary metric:** A two-proportion Z-test to compare session conversion rates.
- **Guardrail metric:** An independent two-sample t-test to compare average time to booking.
- **Effect size analysis:** Relative changes in conversion rate and average time to booking.
- **Decision framework:** Evaluation against predefined rollout criteria using a 90% confidence level (α = 0.10).

### Key Findings

| Metric | Control | Variant | Result |
|---|---:|---:|---|
| Session conversion rate | 15.92% | 18.19% | +14.22% relative change |
| Average time to booking | 15.01 min | 14.89 min | -0.79% relative change |

**Primary metric — Conversion**

The variant achieved a 14.22% relative increase in session conversion rate. The difference was statistically significant (p = 0.0002), providing evidence that the new algorithm improved conversion performance.

**Guardrail metric — Time to booking**

Average time to booking decreased by 0.79% in the variant group. However, the difference was not statistically significant (p = 0.5365). There is no statistically significant evidence that the new algorithm increased the time required to book.

**Sample allocation check**

The session-level allocation check returned a p-value of 0.8524. We fail to reject the null hypothesis of an equal 50/50 session allocation.

### Rollout Decision Criteria

A full rollout is recommended only when both conditions are satisfied:

1. **Primary metric:** The conversion rate improvement is statistically significant (p-value below 0.10) and the effect is positive.
2. **Guardrail metric:** The difference in time to booking is either statistically insignificant (p-value above 0.10) or the effect is favorable (a decrease in booking time).


### Recommendation

Proceed with a full rollout of the new search ranking algorithm, based on the results and decision criteria used in this analysis.
