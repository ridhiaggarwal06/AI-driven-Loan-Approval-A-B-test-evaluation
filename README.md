## Strategic Evaluation of an AI-Driven Credit Risk Model

---

A lending company's existing AI-assisted loan approval model was producing high error rates, creating both missed revenue (rejecting good applicants) and financial risk (approving bad ones). A new model was developed, and a randomized A/B test was run across loan officers over 10 days to determine whether it genuinely improved decision-making, and whether the company should proceed to full rollout.

## Methodology:

### Experimental Design
The company ran a randomized A/B test comparing an existing AI-assisted loan approval model (Control) against a newly developed model (Treatment) over a 10-day period. Randomization was applied at the **loan officer level**, not the individual transaction level — this matters because if the same officer had processed both AI-assisted and non-AI-assisted loans, their decisions could "spill over" between groups, making it impossible to isolate the new model's true effect.

### Data Preparation
The dataset required minimal cleaning, but one issue needed careful handling: a set of zero-value entries in the completion and confidence columns, all concentrated in the Control group. Rather than dropping these rows outright (which would have shrunk the Control group further and biased the comparison), the data was aggregated by officer first, and only rows with genuinely missing totals were removed — preserving group balance and avoiding a skewed comparison.

### Metrics & Evaluation Criteria
Two Overall Evaluation Criteria (OECs) were defined to reflect the business's actual risk-reward tradeoff:
- **Type I Error Rate** — creditworthy applicants wrongly rejected (lost revenue)
- **Type II Error Rate** — high-risk applicants wrongly approved (bad debt risk)

Three additional behavioral metrics were engineered to capture *how* officers interacted with the AI's recommendations: change in agreement, change in conflict, and change in confidence, before vs. after seeing the model's prediction.

### Statistical Testing
Since the comparison involved exactly two groups (Control vs. Treatment), **Welch's t-test** was used rather than ANOVA, which is intended for three or more groups. Welch's variant was chosen over a standard t-test because the two groups had unequal sample sizes (19 vs. 28 officers) — Welch's test doesn't assume equal variances, making it the more defensible choice given that imbalance.

To go beyond statistical significance and assess whether the differences were *practically* meaningful, **Cohen's d** was calculated for both error-rate reductions — both came out large (d = 1.92 and 1.76), indicating the effect wasn't just detectable, but substantial.

### Why This Mattered

A p-value alone tells you a difference likely isn't chance — it doesn't tell you whether that difference is big enough to act on. Pairing significance testing with effect size, and explicitly checking test assumptions (unequal group sizes, unequal variances) rather than defaulting to the standard test, was central to making a rollout-or-wait recommendation the business could actually trust.


### 1. Impact: Fewer Creditworthy Applicants Wrongly Rejected

#### Finding:
The AI model significantly reduced cases where creditworthy applicants were wrongly rejected, approving nearly 45% more “good” customers than the existing system.

#### Why it mattered:
This showed clear revenue upside without increasing customer acquisition costs. For a growing startup, this highlighted a practical way to scale the loan book by capturing customers who were previously being turned away despite being low risk.


### 2. Impact: Fewer High-Risk Loans Approved

#### Finding:
The AI model also approved far fewer high-risk loans, cutting bad approvals by around 32% compared to the legacy process.

#### Why it mattered:
This demonstrated that the model could meaningfully reduce default risk and protect capital. The findings helped frame how AI could improve portfolio health and support long-term sustainability, which is especially important for maintaining investor confidence.

### 3. Behavioral Insight: How Officers Actually Used AI Recommendations

#### Finding:
Loan officers followed AI recommendations more closely over time, even though their personal confidence levels did not increase.

#### Why it mattered:
This surfaced an important behavioral insight: while the AI was influencing decisions, trust in the system had not fully developed. This pointed to the need for better training or explainability, ensuring the technology is integrated thoughtfully rather than blindly adopted.


### 4. Recommendation: Was the Model Ready to Launch?

#### Finding:
Although early results were promising, the data showed high variability due to the short testing window.

#### Why it mattered:
Instead of pushing for immediate rollout, I recommended extending the experiment by a few weeks. This helped avoid premature decisions based on unstable trends and demonstrated a risk-aware approach to deploying AI in a live business environment.

