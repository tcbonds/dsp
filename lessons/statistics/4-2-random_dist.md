[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
rand = np.random.random(1000)
rand_pmf = thinkstats2.Pmf(rand, )
thinkplot.Pmf(rand_pmf, linewidth=.1)
```
![Probability Mass Function](https://github.com/tcbonds/dsp/blob/master/lessons/statistics/chap4pmf.png)

### Explanation:
The plot is filled with vertical lines. This happened because of the nature of graphing many equiprobable random variables in a pmf. Since there is a finite amount of random samples(1000) and each continous value has an equal likelihood, that means that it won't be continuous when plotted. Thus, there are at least 1000 vertical lines filling the plot each with a tiny space in between.  

```python
rand_cdf = thinkstats2.Cdf(rand)
thinkplot.Cdf(rand_cdf)
```
![Probability Mass Function](https://github.com/tcbonds/dsp/blob/master/lessons/statistics/chap4cdf.png)
