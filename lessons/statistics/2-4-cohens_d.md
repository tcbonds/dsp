[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```python

def MyCohenEffectSizeFx(group1, group2):
    '''(Series, Series) -> (float)
    
    Returns Cohen's Effect Size between two groups.
    Equation -> d = mean1 - mean2 / pooled_stdev
    '''
    diff = group1.mean() - group2.mean()
    n1 = len(group1)
    n2 = len(group2)
    
    #pooled variance
    pvar = (n1*group1.var() + n2 * group2.var()) / (n1 + n2)
    
    return diff/np.sqrt(pvar)

d_prglength = MyCohenEffectSizeFx(firsts.prglngth, others.prglngth)
d_totalwgt_lb = MyCohenEffectSizeFx(firsts.totalwgt_lb, others.totalwgt_lb)

print('Cohen\'s Effect Size for total weight(lb): {}'.format(d_totalwgt_lb))
print('Cohen\'s Effect Size for pregnancy length: {}'.format(d_prglength))

```
Cohen's Effect Size for birth weight(lb): -0.088672927072602   
Cohen's Effect Size for pregnancy length: 0.028879044654449883   

### Conclusions:

* The differences are very small between first babies and subsequent babies for both birth weight and pregnancy length.
* There is a larger difference for birth weight than pregnancy length.  
* First babies are lighter and take longer to be delivered.
