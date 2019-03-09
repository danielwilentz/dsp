[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

# My python file:
```
import scipy.stats

mu = 178
sigma = 7.7

res = scipy.stats.norm.cdf(185.4, loc=mu, scale=sigma) - \
      scipy.stats.norm.cdf(177.8, loc=mu, scale=sigma)

print("{} percent of men are in the Blue Man Group".format(str(res*100)))
```

## The results:
34.21% of US men qualify for being in the Blue Man Group
