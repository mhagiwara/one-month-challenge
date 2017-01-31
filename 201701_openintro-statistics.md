# January 2017

https://www.openintro.org/stat/

## 2017/01/01

- pp. 7 - 16
- Statistics is the study of how best to collect, analyze, and draw conclusion from data
- data matrix - common way to organize data with rows for cases and columns for variables
- two types of categorical variables - ordinal (with natural order) and nominal (without it)
- Associated (= dependent) variables

## 2017/01/02

- pp. 17 - 26
- Beware of biases (e.g., non-response bias for surveys, convenience bias)
- Confounding variable - a variable that is correlated with both the explanatory and response variables.
- Stratified sampling (group cases into strata and random sample from each stratum)
- Cluster sample (group cases into clusters and sample a fixed number of clusters)
- Blocking - split cases into blocks based on a variable and make sure to sample from all blocks
- Blind study (participants don't know which group they are in) vs double-blind (researchers don't know either)

## 2017/01/03

- pp. 27 - 36
- A mode - a prominent peak in the distribution. (unimodal = one mode, bimodal = two modes, multimodal = 2+ modes)
- Sample variance (s^2) = sum of deviation^2 / (n - 1) (why n-1? to make it a unbiased estimator of population variance)
- IQR (interquartile range) = length of the 'box' in boxplot = Q3 - Q1
- Whiskers < 1.5 x IQR. Beyond whiskers are outliers
- Median and IQR are robust statistics (to outliers). Sample mean and variance are not.

## 2017/01/04

- pp. 37 - 46
- Contingency table - a table that summarizes for two categorical variables
- Segmented bar plot - visualization of a contingency table (either raw counts or proportion)

## 2017/01/05

- pp. 47 - 54
- Comparing two variables - side-by-side box plot, hollow histogram
- No pie charts!
- Case study: test hypothesis by simulation (gender bias experiment in promotion)

## 2017/01/06

- Lab 0

## 2017/01/07

- pp. 76 - 85
- Probability
    - Probabilities of disjoint events (that cannot happen together) can be added
    - P(A or B) = P(A) + P(B) - P(A and B)

## 2017/01/08

- Lab 1

## 2017/01/09

- Lab 1
- pp. 86 - 95
- Probability
    - Conditional probability, marginal probability, joint probability
    - P(A|B) = P(A,B) / P(B)

## 2017/01/10

- pp. 96 - 105
- Bayes' theorem and mammogram example (false positives)
- Random sampling with and without replacement
- Mean, variance of random variables

## 2017/01/11

- pp. 106 - 115
- Linear combinations of random variables:
    - Mean: E(aX+bY) = aE(X) + bE(Y)
    - Variance: V(aX+bY) = a^2V(X) + b^2V(Y)
- Continuous distribution (density) - area under curve is 1.

## 2017/01/12

- pp. 127 - 130
- Normal distribution
- Z-score - the number of standard deviations from the mean
- Normal distribution table - z-score and their percentiles.

## 2017/01/13

- pp. 130 - 146
- 68 - 95 - 99.7 rule - probability of falling within 1, 2, 3 stdevs from the mean
- Evaluating the normal approximation
    - Normal probability plot (quantile-quantile plot) - see points form a y = x line
- Bernoulli distribution (with two possible outcomes)
- Geometric distribution (number of trials until success)
- Binomial distribution (probability of number of successes in independent trials)

## 2017/01/14

- pp. 147 - 156
- Normal approximation of binomial distribution
- Negative binomial distribution (prob. of observing first success on nth trial)

## 2017/01/15

- pp. 157
- Poisson distribution (Number of occurrences of independent events when the population is large)
- Lab 2: Probability

## 2017/01/16

- pp. 168 - 173
- Chapter 4 - Foundations for inference
- Point estimates (e.g., mean, median, ...)
- Sample distribution - distribution of point estimates from different samples
- Standard error = standard deviation of an estimate = sigma / sqrt(n)

## 2017/01/17

- pp. 174 - 187
- 95% confidence interval: point estimate ± 1.96 SE
- Central limit theorem (informal desc.): sample mean is approximated by normal distribution
- Hypothesis testing using confidence interval
    - Type I error (incorrect rejection of null hypothesis, false positive) and Type II error (incorrect retaining of null hypothesis, false negative)
- Formal testing using p-values
    - p-value = the probability of observing data at least as favorable to the alternative hypothesis as our current data set, if the null hypothesis is true.
- One-sided test (the estimated parameter can only be one side of the benchmark), vs two-sided test
- z test (when the population variance is known): compute z score, and get p-value from the normal distribution table

## 2017/01/18

- pp. 188 - 197
- Two-sided hypothesis testing
    - p-value = left tail + right tail
- Examining the Central Limit Theorem
    - The distribution of sample mean follows normal distribution, no matter what the population distribution is

## 2017/01/19

- pp. 198 - 202
- Unbiased estimator - sampling distribution is centered at the true parameter
- Confidence interval of normal sampling distribution:
    - point estimate ± z* SE  (z* SE = margin or error)
- Test statistic
    - e.g., z-score = when a point estimate is nearly normal

## 2017/01/20

- Lab 3: Distributions

## 2017/01/21

- pp. 219 - 228
- t-distribution - bell-shaped distribution, with fatter tails than normal, with one parameter (degree of freedom) approaches normal distribution when df -> inf
- One sample t-confidence interval: If the sample size is small (n), use t-distribution with n-1 degree of distribution as a coefficient.
- Paired data

## 2017/01/22

- pp. 229 - 238
- Inference for paired data - t-test for differences
- Difference of two means
    - Standard Error of diff. of two means: see Eq. 5.16
    - How to derive this: use var(X+Y) = var(X) + var(Y)

## 2017/01/23

- pp. 239 - 248
- Power calculations for a difference of means
    - power = probability with which we detect the effect
    - Set up null and alternative hypothesis
    - Assume population standard deviation
    - Set "effect size" = the degree of change that we are interested in detecting
    - Calculate probability (area of normal distribution centered at the effect size that are below/above the rejection lines)
- Comparing many means with ANOVA (analysis of variance)
    - Null hypothesis: The mean is the same across all groups
    - Alternative hypothesis: At least one mean is different
    - Why not just do pairwise comparison? We are more tend to make Type 1 Error if first look at two groups (which are most likely outliers) then run statistical test (see: prosecutor's fallacy)

## 2017/01/24

- pp. 249 - 256
- ANOVA (contd.)
    - Mean square between groups (MSG) with associated df (k - 1)
    - Mean square error (MSE)
    - F = MSG / MSE, then run F-test
    - Caution: ANOVA could reject null hypothesis even when there are no groups that are significantly different

## 2017/01/25

- ggplot2 tutorial http://tutorials.iq.harvard.edu/R/Rgraphics/Rgraphics.html
- Introduction

## 2017/01/26

- ggplot2 tutorial
- Geometric objects and aesthetics
- Statistical transformations

## 2017/01/27

pp. 274 - 283
- Inference for categorical data
- Sampling distribution of p (sample proportion) being normal - expect to see at least 10 successes and 10 failures
- SE = sqrt(p(1-p)/n)
- Determining the minimum sample size - use p = 0.5 for the worst case

## 2017/01/28

- pp. 284 - 293
- Chi-square test
    - Z1 = (observed group(1) count - null group(1) count) / SE of observed group(1) count
    - chi-square = z1^2 + z2^2 + ...
    - Use chi-square distribution with df = k - 1 (k = number of groups)

## 2017/01/29

- pp. 294 - 303
- Hypothesis testing S&P 500 daily movements (whether it's independent of the previous day movement)
- Build distribution over days until a 'up' day
    - If independent, this follows a geometric distribution
    - Use chi-square test to compare hypothetical and real distributions
- Two-way tables
    - combinations of outcomes
    - calculate expected counts from table total
    - run chi-square test with df = (# of rows - 1) x (# of columns - 1)
