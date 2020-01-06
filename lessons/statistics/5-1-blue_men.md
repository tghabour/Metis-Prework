[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> REPLACE THIS TEXT WITH YOUR RESPONSE
```python
#import dependencies
import scipy.stats

#model male height distribution in cm with mean 178 cm and st. dev. = 7.7 cm
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

#set min and max allowable heights in cm (convert from imperial units to metric)
min_height_cm = (5*12 + 10)* 2.54
max_height_cm = (6*12 + 1) * 2.54

#calculate probabilities of height below upper and lower bounds, respectively
upper_pct = dist.cdf(max_height_cm)
lower_pct = dist.cdf(min_height_cm)

#calculate probablity of height WITHIN lower and upper bounds
(upper_pct - lower_pct) * 100
```

34.27468376314746
