# AI-driven Loan Approval A/B test evaluation

Business Context:

Lending decisions carry both revenue potential and financial risk. Rejecting reliable borrowers means losing profitable business, while approving high-risk applicants exposes the lender to defaults. To tackle this challenge, a financial services company tested a new AI-assisted loan approval model against the existing system through an A/B experiment. The goal was to evaluate whether the new model reduced decision errors and provided more consistent support to loan officers.


The problem: The dataset contained loan officers’ decisions from both the control group (existing model) and the treatment group (new AI model). The task was to analyse the experiment results to determine whether the new AI system reduced error rates, improved alignment with AI recommendations, and delivered measurable business benefits.


Approach Taken:
- Data Preparation
  - Checked for missing, duplicate, or extreme outliers to ensure valid analysis.
  - Addressed anomalies in decision and confidence variables, especially where zero values clustered in the control group.
  - Summarised loan officer activity into key measures such as number of completed reviews, error rates, and changes in agreement or conflict with AI predictions.

- Evaluation
  - Focused on Type I errors (rejecting good applicants) and Type II errors (approving risky applicants) since these directly affect business outcomes.
  - Applied Welch’s t-tests to compare groups, chosen for its robustness with unequal group sizes.
  - Calculated Cohen’s d effect sizes to measure the practical impact of the results, not just statistical significance.
 

Key Findings:
- Error Reduction:
  - Type I error rate fell from 36.3% to 20.0% (≈45% reduction).
  - Type II error rate dropped from 12.1% to 8.3% (≈32% reduction).
  - Both reductions were statistically significant and had large effect sizes, confirming not only reliability but also meaningful business impact.
  - These metrics were chosen because fewer Type I errors mean more profitable loans approved, while fewer Type II errors reduce the likelihood of defaults.

- Decision Behaviour:
  - Loan officers in the treatment group showed higher alignment with AI recommendations and fewer conflicts with them.
  - Confidence levels did not shift significantly, suggesting the AI improved accuracy without undermining human judgment.

Together, the findings indicate the new AI system meaningfully supports loan officers, helping them make better-quality lending decisions.


Business Impact:
- Lower rejection of good borrowers improves customer satisfaction and revenue.
- Reduced approvals of risky borrowers strengthens the loan book and limits financial exposure.
- Better alignment with AI recommendations suggests the system can act as a trusted assistant rather than a replacement for human expertise.
- Extending the test duration and refining the model with additional economic indicators would make results even more robust before full deployment.
