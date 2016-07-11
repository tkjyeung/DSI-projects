---
title: 1.3 Intro to Stats Models & Scikit-Learn
duration: "1:25"
creator:
    name: Marc Harper
    city: LA
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Stats Models & SKLearn
Week 3 | Lesson 1.3

### LEARNING OBJECTIVES
*After this lesson, you will be able to:*
- Perform a linear regression in scikit-learn
- Perform a linear regression in statsmodels
- Do linear regression on Boston housing dataset with statsmodels, just using a few of the columns, then try again with all of them - does the model get better?


### STUDENT PRE-WORK
*Before this lesson, you should already be able to:*
- Use matplotlib for making scatter plots
- Extract data from pandas DataFrames
- Fit a linear regression for one variable



> This lesson will be heavily code-driven since we're introducing how to use
two new modules.

### LESSON GUIDE
| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Opening](#opening)  | Topic description  |
| 10 min  | [Introduction](#introduction)   | Multilinear Regression |
| 20 min  | [Demo](#demo)  | Python Libraries for Regressions  |
| 25 min  | [Guided Practice](#guided-practice<a name="opening"></a>)  | Statsmodels  |
| 15 min  | [Independent Practice](#ind-practice)  | Practice Regressions |
| 5 min  | [Conclusion](#conclusion)  | Topic description  |

---

<a name="opening"></a>
## Opening (5 mins)
- Review prior labs/homework, upcoming projects, or exit tickets, when applicable
- Review lesson objectives
- Discuss real world relevance of these topics
- Relate topics to the [Data Science Workflow](https://drive.google.com/file/d/0Bx2SHQGVqWasOGY4dE95OFVvZjQ/view?usp=sharing) - i.e. are these concepts typically used to acquire, parse, clean, mine, refine, model, present, or deploy?


<a name="introduction"></a>
## Introduction: Multilinear Regression (10 mins)


In the earlier lesson we went through several fits for models that have one
independent variable. Usually we have more than one independent variable in
our datasets. The way we fit for multiple independent variables is often called
_multilinear regression_ and is conceptually the same. Instead of an equation like

```
y = a + b x
```

where `x` is the independent variable, we instead fit a matrix equation

```
y = X B
```

where `X` is a we have a matrix of independent variables and `B` is a vector
of coefficients like `b`. It's far too tedious to do this by hand so we rely on
one of many software packages to find the best fit coefficients.

Using multiple variables allows us to fit higher dimensional shapes:

```
y = b_0 + b_1 x_1 + b_2 x_2
```

and also more complex curves, like parabolas:

```
y = a  + b x + c x^2
```

What matters is that the relationship between the variables are linear, not the
shape itself. So for the parabola we really have that `x_1 = x` and `x_2 = x^2`.

For equations and images use the [wikipedia page](https://en.wikipedia.org/wiki/Linear_regression), specifically the section "Introduction to linear regression", which lays things out nicely!

**Check:** Translate `y^2 = a x^3 + b x` into a linear regression using three new variables `y_1`, `x_1`, and `x_2`.

> Solution: y_1 = a x_1 + b x_2` where `y_1 = y^2`, `x_1 = x^3`, and `x_2 = x`

## Mean squared error

The mean_squared_error function computes [mean square error](http://en.wikipedia.org/wiki/Mean_squared_error), a risk metric corresponding to the expected value of the squared (quadratic) error loss or loss.
If ![\hat{y}_i](http://scikit-learn.org/stable/_images/math/e8eb12f9407362d0fc035a12094fcc7797dcb69a.png) is the predicted value of the i-th sample, and y_i is the corresponding true value, then the mean squared error (MSE) estimated over ![n_{\text{samples}}](http://scikit-learn.org/stable/_images/math/e088d1aeabf6b6f6608c43bb18829dd7a4097d7f.png) is defined as
![mean square error equation](http://scikit-learn.org/stable/_images/math/b141ee17d93799d1b44c7ba206a859af1a21ba2e.png)


<a name="demo"></a>
## Demo: Python Libraries for Regressions (20 mins)

> Use the included [Starter Code](./code/starter-code/W3-L1.3-starter.ipynb) This is a code-heavy lesson since we are introducing two new python packages, so think of it
as a combination of lesson and lab.


<a name="guided-practice"></a>
## Guided Practice: Statsmodels (25 mins)

[Click through to the following Starter Code](./code/starter-code/W3-L1.3-starter.ipynb)


> Here is the [Solution Code](./code/solution-code/W3-L1.3-solution.ipynb)

<a name="ind-practice"></a>
## Independent Practice: Practice Regressions (15 minutes)

Continue with the starter notebook and practice more model fits.


> [Demo / Starter Code](./code/starter-code/W3-L1.3-starter.ipynb)

> [Solution Code](./code/solution-code/W3-L1.3-solution.ipynb)


<a name="conclusion"></a>
## Conclusion (# mins)
- Review the two modules introduced and explain that we'll use both for many more
models as the course progresses

***

## Additional Resources

- [StatsModels Documentation](http://statsmodels.sourceforge.net)
