[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)


```python
import pandas as pd
import thinkstats2
import nsfg

#read in the data
preg = nsfg.ReadFemPreg()

#select live births only
live = preg[preg.outcome == 1]

#define relevant groups, only interested in series 'totalwgt_lb'
firsts = live[live.birthord == 1]['totalwgt_lb'] 
others = live[live.birthord != 1]['totalwgt_lb'] 

ts2.CohenEffectSize(firsts, others)
'''

-0.088672927072602
