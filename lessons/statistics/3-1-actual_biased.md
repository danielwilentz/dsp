[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

# My python file:
```
import nsfg
import thinkstats2
import thinkplot
from collections import defaultdict as ddict

def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)

    new_pmf.Normalize()
    return new_pmf


resp = nsfg.ReadFemResp()
families = resp.numkdhh

num_children_dict = ddict(int)

for num_children in families:
    num_children_dict[num_children] += 1

pmf = thinkstats2.Pmf(num_children_dict, label='actual')
biased_pmf = BiasPmf(pmf, 'observed')
print(pmf.Mean(), biased_pmf.Mean())

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Show(xlabel='Number of Children per Family', ylabel='PMF')
```

## The results:

Actual Mean: 1.024
Observed Mean: 2.404


