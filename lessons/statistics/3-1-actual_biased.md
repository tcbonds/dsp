[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```python
import matplotlib.pyplot as plt
resp = nsfg.ReadFemResp()

def BiasedPmf(pmf, label):
    '''Returns a new biased pmf that  
    oversamples values in proportion
    to themselves. For example, if we 
    sampled children and asked how many 
    children were in their household, 
    our results would be biased because 
    the larger households have more children 
    and thus, it is more likely to sample 
    children in larger households. Also,  
    we will completely exclude households 
    with no children, because there will be no 
    children in our population.
    '''
    new_pmf = pmf.Copy(label=label)
    
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

children_pmf = thinkstats2.Pmf(resp.numkdhh, label='actual')
bias_pmf = BiasedPmf(children_pmf, label='Observed')
thinkplot.Pmf(children_pmf)
thinkplot.Pmf(bias_pmf)
thinkplot.show(xlabel='Number of Children per Household',
               ylabel='Probability', title='PMF of Children in Respondents\' Household')
```
![](https://github.com/tcbonds/dsp/blob/master/lessons/statistics/PMF%20of%20Children%20in%20Households.png)

```python
print('Actual Mean: {}'.format(children_pmf.Mean()))
print('Observed Mean: {}'.format(bias_pmf.Mean()))
```
Actual Mean: 1.024205155043831  
Observed Mean: 1.024205155043831


