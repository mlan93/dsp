[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Exercise 2.4: Using the variable `totalwgt_lb`, investigate whether first babies are lighter or heavier than others. Compute Cohen’s effect size to quantify the difference between the groups.  How does it compare to the difference in pregnancy length?

#### Examine the means and standard deviations of the first baby and others populations:
```python
print(firsts.totalwgt_lb.mean())
print(others.totalwgt_lb.mean())
print(firsts.totalwgt_lb.std())
print(others.totalwgt_lb.std())
```
```
7.201094430437772
7.325855614973262
1.4205728777207374
1.3941954762143138
```

**On average, first babies are lighter than others. Based on the code above, the mean birth weight for first babies is lower than others (7.20 pounds vs. 7.32 pounds). The lists had standard deviations of 1.42 and 1.39 pounds, respectively.**

#### Compute Cohen's effect size:

```python
def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
 ```

```python
CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb)
```
```
-0.088672927072602
```

**Per the Cohen's effect size of -0.089, first babies are 0.089 standard deviations lighter than others. This is larger than the 0.029 standard deviations noted in pregnancy length, but still smaller than the 1.7 standard deviations noted for the difference in height between men and women.**
