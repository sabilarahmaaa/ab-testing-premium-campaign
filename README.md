# A/B Testing: Evaluating a Premium Campaign

![A/B Testing project overview](assets/ab-testing-project-thumbnail.png)

This educational case study evaluates whether a new Premium campaign variant performed better than the existing campaign in a supplied Spotify scenario. The analysis focuses on the Premium Subscription Rate and checks supporting metrics before recommending a broader rollout.

> **Context:** This project uses an educational dataset and a Spotify campaign scenario. It was not conducted for Spotify. The campaign messaging, target audience, and two-week duration are scenario assumptions.

[View the full analysis presentation](docs/ab-testing-analysis.pdf)

## Decision Question

Does the campaign variant produce a higher Premium Subscription Rate than the control while maintaining the supporting metrics?

## Experiment Overview

| Element | Control | Variant |
|---|---:|---:|
| Users | 50,000 | 50,000 |
| Share of sample | 50% | 50% |
| Campaign | Existing Premium campaign | Proposed targeted campaign |

- **Experiment type:** Superiority test
- **Significance level:** 5% (`alpha = 0.05`)
- **Primary metric:** Premium Subscription Rate
- **Supporting metrics:** Payment Rate, Engagement, and Duration Played

The dataset contains balanced group sizes. A sound experiment would also require random assignment, but the dataset does not document the randomization process.

## Hypotheses

The primary analysis uses a one-sided hypothesis:

- **Null hypothesis (H0):** The Premium Subscription Rate for the variant is less than or equal to the control rate.
- **Alternative hypothesis (H1):** The Premium Subscription Rate for the variant is higher than the control rate.

## Success Criteria

The variant would support a rollout recommendation if:

1. The Premium Subscription Rate increased significantly.
2. Payment Rate, Engagement, and Duration Played did not decrease.

## Methods

| Metric | Metric type | Statistical test |
|---|---|---|
| Premium Subscription Rate | Proportion | Two-proportion z-test |
| Payment Rate | Proportion | Two-proportion z-test |
| Engagement | Continuous | Independent t-test |
| Duration Played | Continuous | Independent t-test |

The original analysis reported that the continuous metrics met the normality assumption before the independent t-tests were applied.

## Results

| Metric | Control | Variant | Relative lift | p-value |
|---|---:|---:|---:|---:|
| Premium Subscription Rate | 59.74% | 80.25% | +34.33% | < 0.0001 |
| Payment Rate | 69.69% | 79.81% | +14.53% | < 0.0001 |
| Engagement | 0.600 | 0.800 | +33.30% | < 0.0001 |
| Duration Played | 120.07 | 159.91 | +33.18% | < 0.0001 |

The Premium Subscription Rate increased by **20.51 percentage points**, from 59.74% to 80.25%. This corresponds to a **34.33% relative lift** over the control rate. The p-value was below 0.0001, so the null hypothesis was rejected at the 5% significance level.

All three supporting metrics were also higher for the variant in the supplied dataset. The analysis found no observed deterioration in the supporting metrics.

## Post-Implementation Monitoring Scenario

The supplied case also includes a short before-and-after comparison:

| Period | Average daily users |
|---|---:|
| Before: 1–7 March 2026 | 16,184 |
| After: 8–15 March 2026 | 24,642 |

The observed average increased by **8,458 users per day**, or **52.26%**. This comparison does not establish that the campaign caused the increase because other factors may have changed between the two periods.

## Recommendation

Proceed with a gradual rollout to a limited user group. Continue monitoring the Premium Subscription Rate and all supporting metrics before expanding the campaign.

The next evaluation should also include revenue and campaign cost data. These measures would show whether the higher conversion and activity translate into a worthwhile business result.

## Limitations

- The dataset does not explain the randomization procedure.
- Detailed campaign information is unavailable.
- The target audience and two-week duration are scenario assumptions.
- The units for Engagement and Duration Played are not defined.
- The post-implementation monitoring period is short.
- Revenue and campaign cost data are unavailable.
- The before-and-after monitoring comparison cannot isolate the campaign’s causal effect.

These limitations reduce how confidently the observed differences can be attributed to the campaign. The recommendation therefore remains conditional on continued monitoring and a stronger experimental record.

## What I Learned

This project strengthened my understanding that statistical significance alone does not determine a product decision. A useful recommendation also depends on experiment design, clearly defined metrics, supporting evidence, and the limits of the available data.

I also learned to treat A/B testing as an iterative process. Results should inform the next rollout, monitoring plan, and experiment rather than serve as a final answer on their own.

## Suggested Next Analysis

- Verify random assignment and group comparability.
- Document metric definitions and units.
- Report confidence intervals and effect sizes alongside p-values.
- Monitor results over a longer period.
- Evaluate revenue, campaign cost, and incremental value.
- Investigate user segments to determine whether the effect is consistent across audiences.

## Author

**Sabila Rahma Utomo**  
Product Manager | Digital Healthcare & Data Analytics  
[GitHub](https://github.com/sabilarahmaaa) | [LinkedIn](https://www.linkedin.com/in/sabilarahmautomo/)
