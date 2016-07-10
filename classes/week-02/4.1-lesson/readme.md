---
title: Stats Review & Intro to SciPy
duration: "1:5"
creator:
    name: Lucy Williams
    city: DC
modified:
    name: Luiz Pizzato
    city: HK
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Stats Review & Intro to SciPy
Week 2 | Lesson 4.1 ..

### LEARNING OBJECTIVES
*After this lesson, you will be able to:*
- Explain what accuracy is
- Explain Type I and Type II errors
- Explain statistical testing
- Run statistical tests in scipy ..

### LESSON GUIDE
| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Introduction](#introduction)   | Accuracy, Type I and Type II errors, ...  |
| 10 min  | [Demo /Guided Practice](#demo)  | Accuracy  |
| 10 min  | [Demo /Guided Practice](#demo)  | Type I and Type II errors  |
| 30 min  | [Demo /Guided Practice](#demo)  | Statistical Testing  |
| 30 min  | [Independent Practice](#ind-practice)  |   |
| 5 min  | [Conclusion](#conclusion)  | Conclusion |

---

<a name="Accuracy, Type I and Type II errors, t-testing"></a>
## Introduction: (5 mins)

- Accuracy:
  - [Accuracy](https://en.wikipedia.org/wiki/Accuracy_and_precision) refers to how close a sample statistic is to a population parameter.
- Type I error.
  - [A Type I](https://en.wikipedia.org/wiki/Type_I_and_type_II_errors) error occurs when the researcher rejects a null hypothesis when it is true.
- Type II error.
  - [A Type II](https://en.wikipedia.org/wiki/Type_I_and_type_II_errors) error occurs when the researcher accepts a null hypothesis that is false.
- [Statistical hypothesis testing](https://en.wikipedia.org/wiki/Statistical_hypothesis_testing)
  - Given two samples calculate how likely that these samples are generated from the same distribution ..

**Check:** Why do you think that accuracy, type I and type II errors, and hypothesis testing are important?

---

<a name="Accuracy"></a>
## Demo/Guided Practice: Accuracy (10 mins)

Accuracy refers to the closeness of a measured value to a standard or known value.
It is often confused with precision, but precision is the closeness of two or more
measurements to each other ..

#### Accuracy versus precision

![AccuracyVersusPrecision](https://upload.wikimedia.org/wikipedia/commons/3/38/Accuracy_and_precision.svg) ..

![AccuracyVersusPrecision](http://www.dnasoftware.com/wp-content/uploads/2015/07/targets.png)

> A good analogy for understanding accuracy and precision is to imagine a basketball
player shooting baskets. If the player shoots with accuracy, his aim will always
take the ball close to or into the basket. If the player shoots with precision, his
aim will always take the ball to the same location which may or may not be close to
the basket. A good player will be both accurate and precise by shooting the ball the
same way each time and each time making it in the basket ..

**Check:** Is it better to be accurate or precise? Why?

---

<a name="Type I and Type II errors"></a>
## Demo/Guided Practice: Type I and Type II errors (10 mins)

Remember we defined a Type I error as an error that occurs when the researcher
rejects a null hypothesis when it is true. The probability of committing a Type I
error is called the significance level , and is often denoted by α (alpha) or *significance level*

Remember we defined a Type II error as an error that occurs when the researcher
do not reject a null hypothesis that is false.  The probability of committing a Type II
error is denoted by β (beta).
- The inverse of β (i.e. 1-β) is called *power* and it defines whether a significant effect can be found for an experiment ..

This table summarizes Type I and Type II errors.

|                 | H0 is valid          | H0 is invalid        |
|:----------------|----------------------|----------------------|
| Reject H0       | Type I error (FP)    | Correct outcome (TP) |
| Don't reject H0 | Correct outcome (TN) | Type II error (FN)   |


 #### Check: Practical Example

A man goes into a trial to decide whether to punish him for a certain crime.

The jury's working hypothesis (H0) is that the man is innocent.

Explain what will happen when the jury's decides according to each of these quadrants.


 |                 | H0 is valid          | H0 is invalid        |
 |:----------------|----------------------|----------------------|
 | Reject H0       | Type I error (FP)    | Correct outcome (TP) |
 | Don't reject H0 | Correct outcome (TN) | Type II error (FN)   |



**Check:** Why are Type I and Type II errors important? ..

#### How many tails?

![Tails](http://i.giphy.com/dcFkdyovzMd8c.gif) ..

- One tailed
  - Is the effect **larger** (or smaller) for the sample than the population?
- Two tailed
  - Is the effect **different** for the sample than the population?

![Tail](https://upload.wikimedia.org/wikipedia/en/0/00/P-value_Graph.png) ..

#### One sample, Two samples, Paired, Unpaired?

- One-sample tests
  - sample compared to population
- Two-sample tests
  - samples are compared to each other
- Paired tests
  - comparing differences between measurements within the same sample after a "treatment" is given to them ..

#### Which test?

- t-test, z-test, chi-squared test, binomial test
- Mann-Whitney U test, Wilcoxon signed-rank test, permutation test

---

<a name="t-testing"></a>
## Demo/Guided Practice: hypothesis testing (30 min) ..

- How would you
  - define if an octopus can predict the outcome of a football game?
  - test if a dice is fair?
  - check if a certain drug had the expected effect?
  - check if a certain strategy has affected a group of people?

**Let's test some of these** ..


### [Paul the Octopus](https://en.wikipedia.org/wiki/Paul_the_Octopus)

![Paul](http://my.fakingnews.firstpost.com/files/2014/06/Paul.jpg)

14 games predicted, 12 correct, 2 incorrect

- What is our null hypothesis? ..

```python
stats.binom_test(12, n=14, p=0.5, alternative='greater')
```

```python
stats.binom_test([12, 2], p=0.5, alternative='greater')
```

**What can you conclude here?** ..

### Fair dice

We suspect a dice is not fair. We roll the dice 60 times and this is the distribution of the faces.

| Face | # times |
| ---- | ------- |
| 1    | 4       |
| 2    | 7       |
| 3    | 9       |
| 4    | 10      |
| 5    | 15      |
| 6    | 15      |


```python
throws = [4,7,9,10,15,15]
chance = len(throws)*[sum(throws)/float(len(throws))] # 6*[10]
stats.chisquare(throws, chance)
```
 ..

### Effect of a drug test

- patients:
  - control (placebo): 50
  - treatment: 50
- mean:
  - control: 100 seconds
  - treatment: 95 seconds
- standard deviation of both: 15 seconds

 ..

```python
n_sample_placebo = 50
n_sample_drug = 50
mean_placebo = 100.0
mean_drug = 95.0
stdev_placebo = 15.0
stdev_drug = 15.0
```

```python
stats.ttest_ind_from_stats(mean_drug, stdev_drug, n_sample_drug,
                           mean_placebo, stdev_placebo, n_sample_placebo,
                           equal_var=True)                           
```
 ..

### Ringing a bell

Does ringing a bell at the start of the class make students arrive at a different time?

![Bell](http://i.giphy.com/sHV6YMsVFTQD6.gif) ..

Here is the data:
```python
before  = [6, 6, 9, -15, 12, -13, -13, 6, -14, 12, 11, 3, 4, -9, 1, 2, -7, 13, -2, -13]
after   = [6, -2, 4, -11, -5, 10, -10, -10, -10, 14, 0, 0, 5, 1, 9, 9, -7, 8, -8, 7]
```

 ..

```python
print np.mean(before), np.std(before)
print np.mean(after), np.std(after)
stats.ttest_rel(before, after)
```

---

<a name="ind-practice"></a>
## Independent Practice: Stat tests (30 minutes)

Can [Mani the Parakeet](https://en.wikipedia.org/wiki/Mani_the_parakeet) predict a football game?

7 games predicted, 5 of them correct ..

There is an energy crisis and the government decided to start a campaign to see if people start using less energy ..

You are given the following summary statistics for samples of a 2-person household:

| Sample | N   | mean (kWh per day)| stdev |
| ------ | --- | ----  | ----- |
| Before | 100 | 14.52              | 5.1   |
| After  | 80  | 14.38              | 5.1   |
| | | | |

**Did the campaign work?**

 ..

 Now what if, N changes to 5,000, and the summary statistic still the same?

 | Sample | N    | mean (kWh per day)| stdev |
 | ------ | ---  | ---- | ----- |
 | Before | 5000 | 14.52             | 5.1   |
 | After  | 5000 | 14.38             | 5.1   |
 | | | | |

 **What can you tell about the campaign now?**

 ..

 What if you have the data, and the samples were actually of the same 100 people who were tested before and after the campaign.

 Here is the data:

 ```python
 consumption_before = [ 19.26840758,  11.44188073,  17.38972849,   7.69844396,
                        12.18108213,  21.64512259,  12.24362028,  16.13276893,
                        21.90487642,  13.37940158,  14.27329186,  22.1564118 ,
                        19.15386648,  10.4928014 ,   9.67887906,  14.87020526,
                        18.97251817,   4.20004753,  11.22015239,   8.87523919,
                        23.75276086,  16.02119543,  16.02285172,   5.61705411,
                         5.36098183,   9.44364401,  11.53455214,  10.95482259,
                         9.62790887,  14.65166201,  11.68984617,  15.46516469,
                        10.26158083,  12.19144943,  11.89947975,  17.76740239,
                         8.10310643,  18.70151844,  18.65734908,  11.79904209,
                        15.6956243 ,  18.95134711,  16.036293  ,  16.19258974,
                        14.28877265,  11.14436601,  18.46169794,  20.26205508,
                        20.94959131,  17.72292331,  24.55788907,  12.46549183,
                        21.7364615 ,   8.95282485,  19.3081868 ,  16.82182098,
                         9.74346686,  15.0062389 ,   2.36499988,  11.20911104,
                        16.96533324,  14.45190775,  16.11600515,  21.21185905,
                        11.08616076,  14.84229029,  23.03728813,  11.12464314,
                        27.36935985,  17.39976249,  -0.32356639,  20.6381818 ,
                        16.8115433 ,  16.09180542,   8.51275636,  16.78976626,
                        12.70716133,  20.48674054,  13.47336418,  10.8147832 ,
                         9.46884467,   8.92483195,  12.21754524,  13.53904906,
                        15.42901916,  14.66892914,  14.5460482 ,   5.62664227,
                        17.00991855,  12.14064696,  18.8474419 ,  21.65959453,
                        15.85824205,  16.73340808,   6.67081132,  17.35712577,
                         9.62791406,  12.25800412,  24.67675621,  16.95424648]
```
 ..

```python
 consumption_after  = [ 19.78279276,  10.62052977,  16.60142694,   7.17703978,
                        12.34354061,  20.86185966,  11.23535532,  16.81372875,
                        21.81657773,  13.46757468,  14.32170947,  21.31407833,
                        18.0955779 ,  10.70637998,   9.80804343,  14.2636665 ,
                        18.94078429,   4.79282487,  11.89252369,   8.59638299,
                        23.24484963,  15.95462362,  15.81983896,   6.23217211,
                         5.73761351,   8.83435037,  11.17110529,  10.33307258,
                         8.98113858,  15.06106432,  12.04808901,  15.53649054,
                        10.34133249,  12.64564181,  12.08834144,  17.71695996,
                         7.8888846 ,  19.26743329,  18.21155548,  11.85583251,
                        15.41341568,  18.80369988,  15.63020783,  16.83109122,
                        14.29761925,  11.26264798,  19.08287025,  19.98172755,
                        20.52667806,  17.74965617,  23.76887908,  13.11906922,
                        21.24608002,   8.79954895,  18.97185511,  17.23417266,
                         9.14506926,  14.41064305,   2.37570565,  11.7666702 ,
                        17.66522569,  13.91526015,  16.42873479,  21.48697148,
                        11.11708899,  14.35974441,  21.98973228,  10.96798601,
                        27.03014106,  17.90519867,  -1.4012036 ,  20.34862684,
                        16.92122095,  16.56342875,   7.72257115,  16.56171961,
                        12.66964192,  20.05906204,  13.35531827,  10.68110683,
                         9.37037086,   8.63057567,  11.52881088,  12.56735504,
                        14.64945827,  14.20890446,  14.37162632,   4.53856206,
                        17.45423203,  11.58674912,  18.48613475,  22.18865715,
                        15.45981571,  16.83639875,   7.05194808,  17.89579456,
                         8.99700663,  11.65867122,  23.98574489,  17.62733494]
 ```

**Did the campaign work now?**

---


<a name="conclusion"></a>
## Conclusion (5 mins)

Now you can:
- Explain what accuracy is
- Explain Type I and Type II errors
- Explain statistical testing
- Run statistical tests in scipy ..
