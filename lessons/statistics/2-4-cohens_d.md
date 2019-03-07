[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

# My python file:
```
import math
import nsfg

# read in the data
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

# isolate first babies and non-first babies
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

def cohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1, var2 = group1.var(), group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

if __name__ == '__main__':
    print(cohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb))
```

## The result:

Cohen's D for first-baby weight to other-baby weight = -0.0886
