Statistical Inference
========================================================

Question 1
==========
When at the free-throw line for two shots, a basketball player makes at least one free throw 90% of the time. 80% of the time, the player makes the first shot, 80% of the time the player makes the second shot and 70% of the time she makes both shots. What is the conditional probability that the player makes the second shot given that she missed the first? Express your answer as a percentage to the nearest percentage point.




Question 2
==========
A web site (www.medicine.ox.ac.uk/bandolier/band64/b64-7.html) for home pregnancy tests cites the following: “When the subjects using the test were women who collected and tested their own samples, the overall sensitivity was 75%. Specificity was also low, in the range 52% to 75%.” Assume the lower value for the specificity. Suppose a subject has a positive test and that 30% of women taking pregnancy tests are actually pregnant. What number is closest to the probability of pregnancy given the positive test? Express your answer to the nearest percentage point.


```r
round((0.75 * 0.3)/((0.75 * 0.3) + ((1 - 0.52) * (1 - 0.3))) * 100)
```

```
## [1] 40
```


Question 3
==========
Suppose that diastolic blood pressures (DBPs) for men aged 35-44 are normally distributed with a mean of 80 (mm Hg) and a standard deviation of 10. What is the probability that a random 35-44 year old has a DBP less than 70? Express your answer as a percentage to the nearest percentage point.

Let X be the number of hits per day. We want P(X≤70) given that X is N(80,10^2).


```r
round((pnorm(70, mean = 80, sd = 10)) * 100)
```

```
## [1] 16
```


Question 4
==========
Brain volume for adult women is normally distributed with a mean of about 1,100 cc for women with a standard deviation of 75 cc. About what brain volume represents the 95th percentile? Express your answer to the nearest cc.

http://www.wolframalpha.com/input/?i=standard+normal+of+95%25

x0=μ+1.64*σ


```r
1100 + (1.64 * 75)
```

```
## [1] 1223
```


or


```r
round(qnorm(0.95, mean = 1100, sd = 75))
```

```
## [1] 1223
```


Question 5
==========
Refer to the previous question. Brain volume for adult women is about 1,100 cc for women with a standard deviation of 75 cc. Consider the sample mean of 100 random adult women from this population. Around what is the 95th percentile of the distribution of that sample mean? Express your answer to the nearest cc.


```r
mean = 1100
n = 100
SD = 75
SE = SD/sqrt(n)
round(mean + (1.65 * SE))
```

```
## [1] 1112
```


or

Question 6
==========
You flip a fair coin 5 times, what's the probability of getting 4 or 5 heads? Express your answer as a percentage to the nearest percentage point.


```r
P4 = choose(5, 4) * 0.5^4 * 0.5^1
P5 = choose(5, 5) * 0.5^5 * 0.5^0
P4or5 = P4 + P5
round(P4or5 * 100)
```

```
## [1] 19
```


Question 7
==========
The respiratory disturbance index (RDI), a measure of sleep disturbance, for a specific population has a mean of 15 (sleep events per hour) and a standard deviation of 10. They are not normally distributed. Give your best estimate of the probability that a sample mean RDI of 100 people is between 14 and 16 events per hour? Express your answer as a percentage point to the nearest percentage.




Question 8
==========
Consider a standard uniform density. The mean for this density is .5 and the variance is 1 / 12. You sample 1,000 observations from this distribution and take the sample mean, what value would you expect it to be near? Give your answer to at least one decimal place.



```r
mean(rnorm(1e+07, mean = 0.5, sd = sqrt(1/12)))
```

```
## [1] 0.5
```


Question 9
==========
Consider a standard uniform density. The mean for this density is .5 and the variance is 1 / 12. You sample 1,000 sample means where each sample mean is comprised of 100 observations. You take the standard deviation of the 1,000 sample means. About what number would you expect it to be? Give your answer to at least 3 decimal places.


```r
round(sqrt(1/12)/sqrt(100), 3)
```

```
## [1] 0.029
```


Question 10
===========
The number of people showing up at a bus stop is assumed to be Poisson with a mean of 5 people per hour. You watch the bus stop for 3 hours. What's the probability of viewing 10 or fewer people? Express your answer to at least two decimal places


```r
round(ppois(10, lambda = 5 * 3), 2)
```

```
## [1] 0.12
```


Question 11
===========
You place 9 balls into a bag labeled 1 to 9 and take three out. How many different combinations of 3 balls (disregarding order) can you get? Express your answer as a whole number.


```r
ncol(combn(1:9, 3))
```

```
## [1] 84
```

