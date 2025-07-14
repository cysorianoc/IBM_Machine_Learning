# Lecture 1: Introduction to Hypothesis Testing and Bayesian Approach

---

## Key Concepts

### What is Hypothesis Testing?
- **Hypothesis**: A statement about a population parameter (e.g., mean arrival rate of customers).
- **Null Hypothesis (H₀)**: The default or specific claim (e.g., average 5 customers per hour).
- **Alternative Hypothesis (H₁)**: The competing claim, often less specific (e.g., more than 5 customers per hour).
- The goal is to decide, based on sample data, whether to **reject H₀** or **fail to reject H₀**.

### Traditional vs Bayesian Hypothesis Testing
- **Frequentist approach**: Provides a decision boundary — either reject or fail to reject H₀.
- **Bayesian approach**: Provides **posterior probabilities** for hypotheses, quantifying how likely each is given the data.

---

## Example: Coin Toss Hypothesis Testing

### Setup
- Two coins:
  - **Coin 1**: P(heads) = 0.5 (fair coin)
  - **Coin 2**: P(heads) = 0.7 (biased coin)
- Unknown which coin is chosen.
- Toss the coin 10 times, observe number of heads.

### Likelihood of Outcomes
- Calculate probability of getting `k` heads out of 10 tosses for both coins.
- Lower heads counts → more likely Coin 1 (fair).
- Higher heads counts → more likely Coin 2 (biased).

### Likelihood Ratio
- Example: Observing 3 heads
  - P(3 heads | Coin 1) = 0.117
  - P(3 heads | Coin 2) = 0.009
- Likelihood ratio = 0.117 / 0.009 ≈ 13 → Coin 1 is 13x more likely to produce this outcome.

---

## Incorporating Priors: Bayesian Hypothesis Testing

- Assign prior probabilities to hypotheses (e.g., P(H₀) = 0.5, P(H₁) = 0.5).
- Use **Bayes’ theorem** to update beliefs:
  
  \[
  P(H_i \mid \text{data}) \propto P(\text{data} \mid H_i) \times P(H_i)
  \]
  
- Posterior probability depends on:
  - Likelihood (from data)
  - Prior belief about each hypothesis
  
- Priors reflect initial knowledge or assumptions (e.g., fair coin is more probable if randomly drawn from public coins).

---

## Summary

- Hypothesis testing frames decision-making about population parameters.
- Bayesian testing contrasts frequentist by providing probabilities of hypotheses rather than a binary decision.
- Coin toss example concretely shows how likelihood and priors combine to update beliefs.
- The likelihood ratio measures which hypothesis better explains the observed data.
- Priors can shift conclusions, highlighting the importance of domain knowledge.

---

## Link to Machine Learning

- **Hypothesis testing parallels model evaluation**: deciding which model (hypothesis) better explains data.
- **Bayesian inference** is foundational in many ML algorithms:
  - Models update parameters based on data (posterior updates).
  - Prior knowledge guides learning and regularization.
- Likelihood ratios relate to **model likelihoods** and **Bayes factors** used in model comparison.
- Understanding hypothesis testing helps grasp concepts like:
  - Overfitting (rejecting null too often),
  - Confidence in predictions (probabilistic reasoning),
  - Bayesian networks and probabilistic graphical models.

---

# Next Steps

The following lectures will cover frequentist hypothesis testing and deepen understanding of decision-making under uncertainty, crucial for both statistics and machine learning.


# Type I vs Type II Errors and Hypothesis Testing

## 1. Hypothesis Testing Basics  
- **Null Hypothesis (H₀):** Usually a statement of "no effect" or "no difference."  
- **Alternative Hypothesis (H₁):** What you want to test for; it suggests there *is* an effect or difference.

---

## 2. Type I Error (False Positive)  
- Occurs when you **reject the null hypothesis when it is actually true**.  
- **Example (coin toss):** The coin is fair, but based on sample data, you mistakenly conclude it's biased.  
- **Business churn example:** You conclude customers who stayed more than 2 years are less likely to churn, but this effect is actually due to chance.

---

## 3. Type II Error (False Negative)  
- Occurs when you **fail to reject the null hypothesis when it is actually false**.  
- **Example (coin toss):** The coin is biased, but you incorrectly conclude it’s fair.  
- **Business churn example:** Customers who stayed more than 2 years *are* less likely to churn, but you fail to detect this and say the churn is due to chance.

---

## 4. Power of a Test  
- **Power = 1 − Probability(Type II error)**  
- The chance of correctly rejecting a false null hypothesis (i.e., detecting an effect when it exists).  
- Power depends on how strict your criteria are to reject the null:  
  - *Too easy to reject null:* High power but more Type I errors.  
  - *Too hard to reject null:* Low power, more Type II errors.

---

## 5. Other Key Terms  
- **Test Statistic:** A calculated value from sample data used to decide whether to reject H₀.  
- **Rejection Region:** Range of test statistic values where you reject H₀.  
- **Acceptance Region:** Range of values where you fail to reject H₀.  
- **Null Distribution:** The distribution of the test statistic assuming H₀ is true.

---

## 6. Business Examples  
- **Marketing Campaign:**  
  - H₀ = campaign has no effect  
  - H₁ = campaign has an effect on purchasing  
- **Website Layout Change:**  
  - H₀ = no impact on traffic  
  - H₁ = change affects traffic  
- **Product Quality:**  
  - H₀ = product size matches expected size  
  - H₁ = product size deviates significantly

---

## 7. Reflection Questions  
- What hypotheses exist in your business context?  
- What data do you need?  
- What exploratory data analysis (EDA) would you do?  
- What approach would you take to test those hypotheses?

---




# Hypothesis Testing Terminology

Let's discuss some more important terminology to keep in mind when discussing hypothesis testing.

**Do we have yet the test statistic?**

- Here, we'll be using the data from the sample to calculate a value that will allow us to determine whether to accept or reject our null hypothesis.
- An example would be the likelihood ratio that we saw earlier when flipping a coin, where if it was a certain value, we would either accept or reject the null hypothesis that we are working with a fair coin.

**Rejection and Acceptance Regions**

- We have the **rejection region**, which is the set of values for the test statistic for which we would reject the null hypothesis.
- We have the **acceptance region**, which is the set of values for the test statistic for which we will accept the null hypothesis.

**Null Distribution**

- The **null distribution** is the distribution of our test statistic, assuming the null hypothesis is true.

---

## Business Examples

**Marketing Intervention**

- For a new direct mail marketing campaign to existing customers:
  - Null hypothesis: The campaign does **not** impact purchasing (no effect).
  - Alternative hypothesis: The campaign **does** have an impact.

**Website Layout**

- Testing whether a change in website layout affects traffic:
  - Null hypothesis: The change had no impact.
  - Alternative hypothesis: The change has an impact on traffic.

**Product Quality or Size**

- Testing if a product meets an expected size threshold \( S \):
  - Null hypothesis: Product size is not significantly different from \( S \).
  - Alternative hypothesis: Product size significantly deviates from \( S \).
- A random sample is taken from each production source, and the hypothesis is tested based on observed means and standard deviations.

---

## Recap

- We discussed trade-offs between **Type I** and **Type II** errors.
- Terminology includes:
  - Test statistic
  - Acceptance region
  - Rejection region
  - Null distribution
- Business examples illustrated hypothesis testing context.
- Reflect on what hypotheses you might test in your business and the data needed.

---

# Significance Level and P-Values

In this section, we discuss **significance levels**, **P-values**, and how to apply them in practice.

### Learning Goals

- Understand classical frequentist hypothesis testing.
- Use significance levels and P-values.
- Discuss importance of sample size and test power.

---

### Null Distribution and Rejection Region

- Knowing the null distribution (e.g., odds of a fair coin) is crucial.
- Calculate the test statistic.
- Choose a **significance level** (\( \alpha \)) *before* testing, linked to the importance of avoiding Type I or Type II errors.
- A lower \( \alpha \) means we reject the null only if the data is very unlikely under the null.

---

### Choosing \( \alpha \)

- Choose \( \alpha \) before computing the test statistic to avoid "P-hacking".
- For critical decisions (e.g., medication safety), use a very low \( \alpha \).
- For less critical decisions (e.g., font size in ads), a higher \( \alpha \) might be acceptable.

---

### Common \( \alpha \) Values

- Typical values: 0.1, 0.05, 0.01, 0.001 (more strict).
  
---

### What is the P-value?

- The probability, under the null distribution, of observing a result as extreme or more extreme than the actual observed result.
- Small P-values indicate data unlikely under the null, leading to rejection of the null.

---

### Confidence Intervals

- Represent values for which we accept the null hypothesis.
- Complementary to P-values and rejection regions.

---

### P-values and Normal Distribution Example

- If \( P = 0.05 \), reject the null if test statistic is beyond ±2 standard deviations from the mean (assuming no effect).
- 95% of values fall within ±2 standard deviations under the null.

---

### Example: Marketing Campaign

- Assume no campaign effect.
- Sample data falling in the extreme 5% tail leads to rejection of the null (campaign has no effect).

---

### Example: Coin Tossing

- Suppose 3 heads in 10 flips.
- Calculate the probability of getting 3 or fewer heads assuming a fair coin (binomial distribution).
- Cumulative probability = 17.1% > 5% cutoff, so **do not reject** the null hypothesis of a fair coin.

---

# Significance Level, P-values, and the F Statistic

### The F-Statistic in Regression

- Null hypothesis: All regression coefficients \( \beta \) = 0.
- Tests if adding features improves prediction beyond the mean outcome.
- Small p-value for F-statistic leads to rejecting null and accepting that features have an effect.

---

### Power and Sample Size

- Running multiple tests increases the chance of at least one **Type I error** (false positive).
- Probability of at least one Type I error ≈ \( 1 - (1-\alpha)^{\text{#tests}} \).
- For example, with 10 tests at \( \alpha=0.05 \), chance of at least one false positive ≈ 40%.

---

### Bonferroni Correction

- To control for multiple comparisons:
  - Adjust \( \alpha \) threshold: \( \alpha_{\text{adjusted}} = \frac{0.05}{\text{# tests}} \).
- This reduces Type I error but lowers test power (harder to detect real effects).
- Larger sample sizes or effect sizes may be needed.

---

### Best Practice

- Limit the number of hypothesis tests to well-motivated cases.

---

## Summary

- Reviewed hypothesis testing with significance levels and P-values.
- Discussed sample size, power, and Bonferroni correction.
- Next lecture will cover implementing hypothesis testing in Python.
