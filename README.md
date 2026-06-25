# Part 2: KPI Framework, Business Experiment Analysis & Decision Recommendation

## Business Context

A subscription-based digital product company launched a new onboarding and activation campaign to improve user conversion and early engagement.

Users were randomly assigned into two groups:

* **Control Group:** Existing onboarding experience
* **Treatment Group:** New onboarding and activation experience

The objective of this experiment was to determine whether the new onboarding experience should be launched to all users.

---

# Business Problem Statement

The company must decide whether the new onboarding and activation campaign should replace the existing onboarding experience.

### Decision To Be Made

Determine whether the Treatment onboarding experience should be launched to all users.

### Who This Decision Impacts

* Product Team
* Marketing Team
* Revenue Team
* Customer Support Team
* New Users

### Metric That Should Improve

The primary metric that should improve is **Paid Conversion Rate**, which measures the percentage of users who become paying subscribers.

### Risks That Must Be Monitored

* Increased refund requests
* Increased support ticket volume
* Lower quality conversions
* Poor user experience
* Segment-specific performance decline

### Evidence Required Before Recommendation

* Conversion rate comparison between Control and Treatment groups
* Statistical significance testing
* Revenue and engagement analysis
* Guardrail metric evaluation
* Segment-level analysis

---

# Dataset Description

Dataset File:

`data/campaign_experiment_data.xlsx`

The dataset contains user-level experiment data including:

* User ID
* Experiment Group
* Landing Page Visits
* Trial Starts
* Onboarding Completion
* Paid Conversions
* Revenue
* Refund Requests
* Support Tickets
* Engagement Score
* Days To Convert
* Region
* Device Type
* Traffic Source

---

# North Star Metric

## Paid Conversion Rate

### Formula

Paid Conversion Rate = Paid Users ÷ Total Users

### Why It Was Selected

Paid Conversion Rate directly measures the success of converting users into paying customers.

This metric has the strongest connection to subscription growth and long-term revenue generation.

### Why Other Metrics Are Supporting Metrics

The following metrics explain user behavior but are not the primary business outcome:

* Landing Page Visit Rate
* Trial Start Rate
* Onboarding Completion Rate
* Engagement Score
* Revenue Metrics

These metrics influence conversion but do not directly represent business success.

### Connection To Business Growth

Higher conversion rates lead to:

* More paying subscribers
* Increased recurring revenue
* Better customer acquisition efficiency
* Sustainable business growth

### Risk Of Optimizing Blindly

If conversion is optimized without guardrails:

* Refund rates may increase
* Support tickets may increase
* Customer satisfaction may decline
* Low-quality users may convert and churn

Therefore guardrail metrics must also be monitored.

---

# KPI Tree Summary

## North Star Metric

Paid Conversion Rate

### Driver 1: Acquisition Quality

* Landing Page Visit Rate
* Traffic Source Quality

### Driver 2: Activation Quality

* Trial Start Rate
* Onboarding Completion Rate

### Driver 3: User Engagement

* Engagement Score
* Days To Convert

### Driver 4: Revenue Quality

* Average Revenue Per User
* Average Revenue Per Converted User

### Guardrail Metrics

* Refund Rate
* Support Ticket Rate
* Segment-Level Decline

KPI Tree Image:

`outputs/kpi_tree.png`

---

# Data Cleaning And Preparation

The dataset was reviewed and validated before analysis.

### Checks Performed

#### Missing Values

No significant missing values were identified.

#### Group Counts

Control and Treatment groups contained balanced user counts.

#### Duplicate User IDs

No duplicate user IDs were detected.

#### Invalid Binary Values

No invalid binary values were identified.

#### Revenue Outliers

Revenue values were reviewed for extreme observations.

#### Segment Distribution

Region, device type, and traffic source distributions were reviewed across groups.

### Outcome

The dataset was considered suitable for experiment analysis.

---

# Experiment Analysis Summary

## Control vs Treatment Comparison

| Metric                             | Control | Treatment |
| ---------------------------------- | ------: | --------: |
| User Count                         |     693 |       715 |
| Landing Page Visit Rate            |  63.64% |    72.59% |
| Trial Start Rate                   |  25.11% |    29.09% |
| Onboarding Completion Rate         |  15.58% |    21.26% |
| Paid Conversion Rate               |   3.17% |     6.99% |
| Average Revenue Per User           |   51.75 |     53.88 |
| Average Revenue Per Converted User | 1630.10 |    770.41 |
| Refund Rate                        |   0.00% |     0.42% |
| Support Ticket Rate                |  14.72% |    24.76% |
| Average Engagement Score           |   57.03 |     62.93 |
| Average Days To Convert            |    8.86 |      6.40 |

Segment analysis was also completed for:

* Region
* Device Type
* Traffic Source

Results are available in:

`outputs/experiment_summary.xlsx`

---

# Hypothesis Test Summary

## Null Hypothesis (H0)

There is no statistically significant difference in paid conversion rates between the Control and Treatment groups.

## Alternative Hypothesis (H1)

The Treatment group has a higher paid conversion rate than the Control group.

## Test Type

One-Tailed Two-Proportion Z-Test

## Significance Level

Alpha = 0.05

## Metric Tested

Paid Conversion Rate

## Reason For Choosing This Metric

Paid Conversion Rate is the North Star metric and directly impacts business growth and revenue generation.

## Test Results

| Metric                    | Value   |
| ------------------------- | ------- |
| Control Conversion Rate   | 3.17%   |
| Treatment Conversion Rate | 6.99%   |
| Z Statistic               | 3.25    |
| P Value                   | 0.00115 |

## Decision Rule

* If P Value < 0.05 → Reject H0
* If P Value ≥ 0.05 → Fail to Reject H0

## Statistical Decision

Since 0.00115 < 0.05, the null hypothesis was rejected.

## Business Interpretation

The Treatment onboarding experience significantly improved paid conversion performance compared to the Control experience.

---

# Guardrail Metrics Evaluation

The recommendation was not based solely on conversion improvement.

The following guardrail metrics were evaluated:

| Metric                  | Observation                    |
| ----------------------- | ------------------------------ |
| Refund Rate             | Slight Increase                |
| Support Ticket Rate     | Increased, Requires Monitoring |
| Average Days To Convert | Improved                       |
| Engagement Score        | Improved                       |
| Revenue Quality         | Stable                         |

### Risk Assessment

No guardrail metric created a critical risk that would prevent rollout.

However, support ticket volume and refund rates should continue to be monitored after launch.

---

# Final Recommendation

## Recommendation: Launch Treatment

### Supporting Reasons

* Paid conversion rate increased from 3.17% to 6.99%.
* Statistical testing confirmed significance.
* Engagement improved.
* Users converted faster.
* Revenue per user increased.
* Positive results were observed across multiple segments.

### Risks And Limitations

* Support ticket volume increased.
* Refund rates increased slightly.
* Results are based on the experiment period only.
* Future user behavior may differ.
* Statistical significance does not automatically prove causation.

### Next Steps

1. Launch the Treatment onboarding experience.
2. Monitor refund and support ticket trends.
3. Continue segment-level performance reviews.
4. Run follow-up experiments.
5. Evaluate long-term retention and revenue impact.

---

# Screenshots Included

* screenshots/summary_metrics.png
* screenshots/hypothesis_test_output.png
* screenshots/kpi_tree_preview.png

These screenshots provide evidence of KPI development, experiment analysis, and hypothesis testing.

---

# Repository Structure

part2_kpi_experiment/

├── data/
│   └── campaign_experiment_data.xlsx

├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md

├── outputs/
│   ├── kpi_tree.png
│   ├── experiment_summary.xlsx
│   └── recommendation_memo.md

├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png

└── README.md
