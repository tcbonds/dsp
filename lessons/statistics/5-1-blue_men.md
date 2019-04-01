[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```python
import scipy.stats

# Creating analytic normal distribution of heights
mu = 178
sigma = 7.7
height_dist = scipy.stats.norm(loc=mu, scale=sigma)

def ftandin_to_cm(ft, inch):
    '''Return a height in inches
    from parameters of ft and inches.
    '''
    total_inch = ft*12 + inch
    return total_inch*2.54

# Finding Z-Score/percentile of lower bound
lower_z_score = (ftandin_to_cm(5, 10) - mu) / sigma
lower_percentile = scipy.stats.norm.cdf(lower_z_score)

# Finding Z-Score/percentile of lower bound
upper_z_score = (ftandin_to_cm(6, 1) - mu) / sigma
upper_percentile = scipy.stats.norm.cdf(upper_z_score)

# Finding difference between upper and lower percentiles
final_percentile = (upper_percentile - lower_percentile) * 100
print('{}% of people are between 5\'10" and 6\'1"'.format(final_percentile))
```
**34.27468376314746% of people are between 5'10" and 6'1"**
