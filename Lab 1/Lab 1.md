# Lab 1

### Question 1
Given the normal distribution: $f(x) := \frac{1}{\sqrt{2 \pi} \sigma} \textrm{e}^{\frac{-(x-\mu)^2}{2\sigma^2}}$ and $x=1.2$, we compute and choose the largest value for the proposed $\sigma$ and $\mu$ for: $$L(\mu,\sigma):=f(1.2)= \frac{1}{\sqrt{2 \pi} \sigma} \textrm{e}^{\frac{-(1.2-\mu)^2}{2\sigma^2}}.$$
 
 - $L(0,1) = \frac{1}{\sqrt{2 \pi}} \textrm{e}^{\frac{-(1.2)^2}{2}}\approx 0.194$
 - $L(0,0.5) = \frac{1}{\sqrt{2 \pi} \cdot 0.5} \textrm{e}^{\frac{-(1.2)^2}{2 \cdot 0.5}}\approx 0.0447$
 - $L(1,2.5) = \frac{1}{\sqrt{2 \pi} \cdot 2.5} \textrm{e}^{\frac{-(1.2-1)^2}{2}}\approx 0.159$

Hence we see that $L(0,1)$ achieves the greatest value and the standard normal distribution is most likely where the simulated normal random variate comes from. 

### Question 2

Returning to the previous question, suppose I remember that the standard deviation is actually 2.5, but I am not sure that the mean is really 1. Can I use maximum likelihood estimation to estimate $\mu$ in this case? If so, what should my estimate of $\mu$ be? 

**Answer:**
Yes, we can use Maximum Likelihood Estimation (MLE)

assuming that observation comes from a normal distribution $X \sim N(\mu, \sigma^2)$

Since $\sigma$ is fixed at 2.5 and we have an observation $x = 1.2$, we maximize the likelihood function with respect to $\mu$.

 (pdf) of a normal distribution is:
$$f(x) = \frac{1}{\sqrt{2\pi}\sigma} \exp\left( -\frac{(x - \mu)^2}{2\sigma^2} \right)$$

As observed value is $x = 1.2$, the likelihood function is:
$$L(\mu, \sigma) = f(1.2) = \frac{1}{\sqrt{2\pi}\sigma} \exp\left( -\frac{(1.2 - \mu)^2}{2\sigma^2} \right)$$

Taking log gives the log-likelihood function:
$$\ell(\mu, \sigma) = \log L(\mu, \sigma) = -\log(\sigma) - \frac{1}{2}\log(2\pi) - \frac{(1.2 - \mu)^2}{2\sigma^2}$$

For any fixed $\sigma > 0$, this expression is maximized when $(1.2 - \mu)^2$ is minimized. This occurs when:
$$\hat{\mu} = 1.2$$

### Question 3
Suppose I really have no idea what $\mu$ and $\sigma$ should be. Can I still estimate them? If not, can I estimate $\mu$?

**Answer**

**Estimating both $\hat{\mu}$ and  $\sigma$:** With only $n=1$ observation, we cannot effectively estimate both parameters simultaneously

While the MLE for the mean remains $\hat{\mu} = 1.2$, the likelihood for $\sigma$ does not have a well-defined maximum; as $\sigma \to 0$, the likelihood goes to infinity.

**Estimating $\mu$ only:** If we treat $\sigma$ as an unknown but fixed constant, we can still estimate $\mu = 1.2$, as it remains the value that makes the observed data most probable.

### Question 4


As the question says, both techniques have mean error = 0, so the sample mean is an unbiased estimator of \(\mu\).
To compare which method is better, we compare the **standard error** of the sample mean.

With a budget of \$1000:

Technique 1 costs \$10 per measurement, so

$$
n_1 = \frac{1000}{10} = 100.
$$

Technique 2 costs \$2.50 per measurement, so

$$
n_2 = \frac{1000}{2.5} = 400.
$$

The standard error of the sample mean is

$$
SE(\bar{X}) = \frac{\sigma}{\sqrt{n}}.
$$

For technique 1 ($\sigma$ = 20\).

$$
SE_1 = \frac{20}{\sqrt{100}} = \frac{20}{10} = 2.
$$

For technique 2 ($\sigma$ = 50\),

$$
SE_2 = \frac{50}{\sqrt{400}} = \frac{50}{20} = 2.5.
$$

Since \(SE_1 < SE_2\), technique 1 gives a more precise estimate of $\mu$.

This shows that a bigger sample size is **not always** better: if each measurement is much noisier, the mean estimate can still be worse even with more data. therefore we should choose the standard error.
 
    
### Question 5

#### a)


#### b)


#### c)



