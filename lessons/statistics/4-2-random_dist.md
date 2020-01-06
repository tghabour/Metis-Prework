[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
#import dependencies
import numpy as np
import thinkstats2 as ts2
import thinkplot as tp

#create sample of 1000 random numbers 
rand_samp = np.random.random_sample((1000,))

#create pmf and cdf
rand_pmf = ts2.Pmf(rand_samp)
rand_cdf = ts2.Cdf(rand_samp) 

#plot PMF
tp.Pmf(rand_pmf)
tp.Config(xlabel='Random Value', ylabel='PMF')

#plot CDF
tp.Cdf(rand_cdf)
tp.Config(xlabel='Random Value', ylabel='CDF')
```
