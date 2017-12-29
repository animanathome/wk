## Standard Normal distribution

The standard normal distribution (also known as the **Z distribution**) is the normal distribution with a mean of zero and a variance of one (the green curves in the plots to the right). It is often called the bell curve because the graph of its probability density looks like a bell.

Many values follow a normal distribution. This is because of the **central limit theorem**, which says that if an event is the sum of other random events, it will be normally distributed.

### Z-score
Simply put, a z-score is the number of standard deviations from the mean a data point is. But more technically it's a measure of how many standard deviations below or above the population mean a raw score is. A z-score is also known as a standard score and it can be placed on a normal distribution curve

### Critical Z-value
(-2.33, 2.33) are the critical values of Z for a 98% confidence, (-1.96, 1.96) in case of a 95% confidence. If the z-score falls outside this range the we reject the null hypothesis. 

### True or False
- The alpha level is smaller for smaller critical regions: **True**
- The critical region defines unlikely values if the null hypothesis is true: **True**
- When the z-score is large (e.g. more then 3.00), we accept the null hypothesis: **False** - should be within the confidence bounds 
- A decision to retain the null means that you believe the treatment has no effect, based on your sample: **True** - no change == null hypothesis
- An effect that exists is more likely to be detected if n is large: **True**
- An effect that exists is less likely to be detected is \\\(\sigma\\\) is large: **True**

### Conclusion
Z-test works when we know \\\(\mu\\\) (mean) and \\\(\sigma\\\) (standard deviation) samples.
- How different a sample mean is from a population
- How different 2 sample means are from each other: dependent vs independent

### Formula

- Median is the value at position \\\((n+1)/2\\\)
- Mean ("average"): \\\(\mu = \frac{1}{n}(\sum_{n=1}^n\{x_i})= \frac{x_1 + x_2 + ... + x_n}{n}\\\)
- Standard Deviation ("variability"): \\\(\sigma = \sqrt{\frac{\sum{(x_1 - x_2)^2}}{n}}\\\)
- Variance: \\\(v = \sigma^2\\\)
- Z-score: \\\(z = \frac{\bar{x}-M}{\frac{\sigma}{\sqrt{n}}}\\\)
- Alpha or \\\(\alpha\\\) = .05 or 5% in case of a 95% confidence


### Code

```
import numpy as np
import scipy.stats as st

x = 8.3 # sample mean
n = 50 # sample size

m = np.mean(data)
print('mean {}'.format(m))

std = np.std(data)
print('standard deviation {}'.format(std))

# t-critical lower and upper bounds when 95%|2-tailed
tcl = st.norm.ppf(0.025) 
tcu = st.norm.ppf(0.975)
print('t critical ({},{})'.format(tcl, tcu)

z = (x - m) / (dst / np.sqrt(n))
print('z-score {}'.format(z))

p = 1.-st.norm.cdf(z)
print('probability {}'.format(p))
```
