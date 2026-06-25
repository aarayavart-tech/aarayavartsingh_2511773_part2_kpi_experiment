# Hypothesis Test Notes

## Business Objective

The purpose of this experiment is to determine whether the new onboarding and activation campaign improves paid conversion rates compared with the existing onboarding experience.

The business decision is whether the treatment experience should be launched to all users.

---

# Primary Metric Tested

## Paid Conversion Rate

Formula:

Paid Conversion Rate = Paid Users ÷ Total Users

This metric was selected because it directly impacts subscription growth and revenue generation.

An increase in paid conversion rate indicates that more users are successfully progressing from onboarding to becoming paying customers.

---

# Null Hypothesis (H0)

There is no statistically significant difference between the paid conversion rates of the Control and Treatment groups.

H0:

Treatment Conversion Rate = Control Conversion Rate

---

# Alternative Hypothesis (H1)

The Treatment group has a higher paid conversion rate than the Control group.

H1:

Treatment Conversion Rate > Control Conversion Rate

---

# Test Type

One-tailed Two-Proportion Z-Test

A one-tailed test was selected because the business objective is specifically to determine whether the treatment increases conversion performance.

---

# Significance Level

Alpha = 0.05

Confidence Level = 95%

---

# Test Inputs

| Metric           | Control | Treatment |
| ---------------- | ------- | --------- |
| Users            | 693     | 715       |
| Paid Conversions | 22      | 50        |
| Conversion Rate  | 3.17%   | 6.99%     |

---

# Test Results

| Metric             | Value   |
| ------------------ | ------- |
| Z Statistic        | 3.25    |
| P Value            | 0.00115 |
| Significance Level | 0.05    |

---

# Decision Rule

If P Value < 0.05:

Reject the Null Hypothesis

If P Value ≥ 0.05:

Fail to Reject the Null Hypothesis

---

# Statistical Decision

P Value = 0.00115

Since:

0.00115 < 0.05

The Null Hypothesis is rejected.

---

# Business Interpretation

The Treatment group achieved a significantly higher paid conversion rate than the Control group.

The observed improvement is unlikely to have occurred due to random chance.

The new onboarding and activation campaign appears to have a positive effect on user conversion performance.

The Treatment experience increased conversion from 3.17% to 6.99%, representing a meaningful improvement in subscription acquisition.

---

# Guardrail Metrics Considered

The recommendation should not be based only on conversion improvement.

The following guardrail metrics were also reviewed:

* Refund Rate
* Support Ticket Rate
* Average Days To Convert
* Engagement Score
* Revenue Quality

These metrics help ensure that conversion improvements are not creating unintended negative consequences for customers or business performance.

---

# Risks and Limitations

* Statistical significance does not automatically prove causation.
* Results are based on the observed experiment period.
* User behavior may change over time.
* Segment-level performance differences should be monitored after launch.

---

# Conclusion

The experiment provides strong statistical evidence that the Treatment onboarding experience improves paid conversion performance.

Because the p-value is substantially below the 0.05 significance threshold, the Treatment experience should be considered for rollout, subject to review of guardrail metrics and ongoing monitoring after implementation.
