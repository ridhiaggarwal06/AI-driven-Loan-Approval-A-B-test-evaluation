## AI-driven Loan Approval A/B test evaluation

#### Project Overview
This project analyses the results of a 10-day A/B test conducted at a consumer lending company to evaluate whether a new AI-assisted loan approval model improves loan officers’ decision quality compared to the existing system.

The goal was to determine if the new model:
* Reduces financial risk
* Improves approval accuracy
* Should be deployed at scale

#### Business Problem
Loan officers were producing high error rates, leading to:
* Lost revenue from rejecting good applicants (Type I errors)
* Financial losses from approving risky applicants (Type II errors)
A new AI model was introduced, and an A/B test was run to measure whether it meaningfully improves decision-making over the current system

#### Experiment Design
* Control group: Loan officers using the existing AI model
* Treatment group: Loan officers using the new AI model
* Randomisation unit: Loan officer (to prevent spillover effects)
* Duration: 10 days
* Key outcomes measured:
  - Type I error rate
  - Type II error rate
  - Agreement with AI recommendations
  - Conflict with AI recommendations
  - Decision confidence
 
#### Data Preparation & Feature Engineering
* Dataset was pre-cleaned, with no major missing or duplicate values detected.
* Zero-value anomalies were handled carefully to avoid bias between control and treatment groups.
* Key engineered variables included:
  - Change in agreement with AI
  - Change in conflict with AI
  - Change in confidence after AI assistance
* Created error rates per loan officer to fairly compare performance across groups.

#### Analysis Methods
* Aggregated performance at the loan officer level
* Used Welch’s two-sample t-tests to compare:
  - Type I error rates
  - Type II error rates
* Calculated:
  - Overall Evaluation Criteria (OEC)
  - Net improvement
  - Effect size (Cohen’s d) for practical significance
* Visualised group differences using ggplot2

#### Key Results
* Type I errors reduced by ~45% in the Treatment group
* Type II errors reduced by ~32% in the Treatment group
* Loan officers showed:
  - Higher agreement with AI
  - Lower conflict with AI
* Large effect sizes confirmed that the results were not only statistically significant but also practically meaningful.

#### Business Interpretation
The new AI model:
  - Approves more creditworthy customers
  - Reduces approval of high-risk loans
  - Improves decision consistency
  - Lowers overall financial risk
This supports the model’s value as a decision-support tool, not just a prediction system

#### Recommendations
* Extend the experiment duration (2–4 weeks) to stabilise confidence intervals
* Increase the number of loan officers to improve statistical power
* Consider a refined hybrid system (AI + rule-based thresholds) before full automation
* Run a follow-up A/B test using updated economic indicators
