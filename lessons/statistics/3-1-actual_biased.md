[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

```python
# import dependencies
import nsfg
import thinkstats2 as ts2
import thinkplot as tp

#retreive data
resp = nsfg.ReadFemResp()
numkdhh_hist = ts2.Hist(resp['numkdhh'])

#defined Biased PMF
def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf
   
#create unbiased and biased PMFs
unbiased_pmf = ts2.Pmf(numkdhh_hist, label='unbiased')
biased_pmf = BiasPmf(unbiased_pmf, label='biased')

#thinkplot.PrePlot(2)
tp.Pmfs([unbiased_pmf, biased_pmf])
tp.Config(xlabel='NUMKDHH', ylabel='PMF')
