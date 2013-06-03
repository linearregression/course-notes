# Statistics intro
Moving from informatics to analytics

Statistical inference = methods for drawing conclusions about a population from sample data
* hypothesis tests
* confidence intervals

Hypothesis testing
* compare experimental and control groups
* null hypothesis: no difference
* alternative hypothesis: there is a statistically significant difference between the groups for some test statistic
* careful experimental design

Type 1 error: null is true but it is rejected (false negative) - ALPHA
Type 2 error: null is false but not rejected (false positive) - BETA
1 - BETA is the statistical power of the test

# Publication bias
p-value = odds that the difference between two treatments is not just chance
two-sided test == absolute value
one-sided test == looking at only greater or lesser than a value
typical cutoff is 0.05 for significance

publication bias = people don't publish negative results; can explain "decline effect" because only positive studies are published, and as group sizes increase you get more accurate data about the absence of an effect

# Effect size meta-analysis
effect size = (mean of experimental group - mean of control group) / standard deviation
standard deviation has to be estimated:
* take stdev of control group
* or more complicated 

small effect size is 0.2, medium is 0.5, large is 0.8
Confidence interval of effect size: if repeat the experiment 100 times, the interval would include the effect size measurement 95 times; if the interval includes 0.0, then the result is not statistically significant

Meta-analysis: weighted average of independent studies
* weight by sample size
* inverse-variance weight
* etc

Heteroskedasticity = when variance itself is not constant
* may not be a problem
* can increase overall error estimates, can lead to Type 2 errors
