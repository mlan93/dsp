[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Exercise 2.4: Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. Compute Cohen’s effect size to quantify the difference between the groups.  How does it compare to the difference in pregnancy length?

#### Examine the means and standard deviations of the first baby and others populations:
```python
print(firsts.totalwgt_lb.mean())
print(others.totalwgt_lb.mean())
print(firsts.totalwgt_lb.std())
print(others.totalwgt_lb.std())
```

On average, first babies are lighter than others. Based on the code above, the mean birth weight for first babies is lower than others (7.20 pounds vs. 7.32 pounds). The lists had standard deviations of 1.42 and 1.39 pounds, respectively.

#### Compute Cohen's effect size:
```python
CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb)
```

Per the Cohen's effect size of -0.089, first babies are 0.089 standard deviations lighter than others. This is larger than the 0.029 standard deviations noted in pregnancy length, but still smaller than the 1.7 standard deviations noted for the difference in height between men and women.
